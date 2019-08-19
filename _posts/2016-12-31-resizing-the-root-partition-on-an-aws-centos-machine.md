---
layout: post
cover: 'assets/images/cover-cloud.jpg'
navigation: True
title: Resizing the root partition on an AWS CentOS machine
date: 2016-12-31 23:20
tags: sysadmin centos technical aws 
subclass: 'post tag-sysadmin tag-centos tag-technical tag-aws'
logo: 'assets/images/ghost.png'
author: 'michiel'
categories: michiel 
---

Many who use CentOS6 as their operating system of choice for their EC2s have probably come across this issue. I certainly have and therefore decided to write a blog post about how to deal and overcome this situation.

For example you started to setup your EC2 instance, and when you had to specify the disk size you entered 20GB. Once the machine was up and running, you noticed soon that you start to run out of disk space. How is this possible?

A quick look at your system shows you the following:

    # df -h /dev/xvda1
    Filesystem      Size  Used Avail Use% Mounted on
    /dev/xvda1      7.8G  3.3G  4.1G  45% /

    # fdisk -l
    Disk /dev/xvda: 21.5 GB, 21474836480 bytes
    [...]

The biggest problem is that the CentOS images seemingly are configured to use an 8 GB root partition. This is of course not really the right way to configure an instance. A good configured image (see the Ubuntu AWS Images for example) will take the size of the root volume in its entirety.

***Why is this a problem?*** Could you not add more partitions and move the needed data into those partitions?

Yes, you can. However consider the following scenario: You have decided that for your new EC2 instance, you will need a 20GB root volume to host all your data and dependencies. It makes you need to do several additional steps to make everything work out of the box, for something that should work out of the box begin with.

***What is the cause of this?*** It seems the reason for this is, at least in the CentOS6 images (I have read, but not tested) that this is corrected in the CentOS7 image), the package **`cloud-utils-growpart'** has been absent from the actual image. Thus, CentOS6 literally lacks the ability to scale up to whatever size you specified.

Secondly; yes, you could move partitions around and move directories in newly created partitions. However that is not the point here that you specified a single partition of a particular size. You did not opt for having multiple partitions.

### The Solution

There are basically two methods that work. Which one you want to use depends quite how brave and adventurous you are feeling:

In any case, ***safety*** first:
Create an AMI image from the original machine. This will stand you in good stead in case something goes horribly wrong and you can spin up an instance from that.

[The safest method](https://forums.aws.amazon.com/thread.jspa?messageID=212121):

* Start by shutting down the instance on which you want the disk to resize

* Detach the Elastic Block Storage Volume (EBS) from the EC2 Instance. Make a note of the Volume-ID and where the disk is mounted.
  (in most cases this will be /dev/sda1 (also known as /dev/xvda1 on the actual instance))

* Re-attach the disk to another running instance (or spin one up for this).
  (in most cases AWS will assign this something like /dev/sdf or /dev/sdg as the device)

* Use tools like `parted` to grow the partition and `resize2fs` to extend the file system.

* Detach and reattach the volume to the original instance and start it up.

There are some other ways you can expand on this scenario to keep your data as safe and stable as possible (detach the original volume and attach the AMI volume/newly created volume in place). That is, as they say, an exercise I will leave to the imagination of the systems-administrator.


[The slightly more adventerous method](https://forums.aws.amazon.com/message.jspa?messageID=547507#547507):

* Start fdisk for that disk (xvda, so not the partition xvda1)<br>
`fdisk /dev/xvda1`

* Switch to sector display<br>
`u`

* Print the partition(s), and remember the start sector (2048 in the example).<br>
`p`

* Delete the partition. (*don't worry this will not delete your data*)<br>
`d`

* Create a new partition, and make it a primary partition, and make it the first one (so it will be /dev/xvda1 on reboot)<br>
`n` (*create a new partition*)<br>
`p` (*make it a primairy partition*)<br>
`1` (*first partition*)

* Enter the old start sector, do NOT make any typo here!!! (*2048* in the example), for the new size, I would suggest you hit enter to accept the default. This will be the remainder of the disk as it should be.

* Print the changes and make sure the start sector is ok, if not restart the procedure. Everything is not changed until you write the information back to disk.<br>
`p` (*print the partition table*)

* Make the partition bootable. do ***NOT*** forget this!!! and select your partion.<br>
`a` (toggle a bootable flag*)
`1`

* Write the partition info back, this will end the fdisk session.<br>
`w`

* Reboot the server, and wait for it to come up (this may take longer than usual).

Verify the file-system size. If the file-system is not around 20Gb as expected, you can use this command:<br>
`resize2fs /dev/xvda1`

This should see you quickly back up and running. I have used the second method and found it all in all to be rather painless.

### Final Notes

As a workaround until cloud-utils-growpart gets built into the AMI you can put the following in your instance's user-data.

    >>> cloud-boothook

    #!/bin/bash
    yum install -y cloud-utils-growpart

Secondly, The latest CentOS7 images seem to have cloud-utils-growpart build in. So this means that the above will not happen if you run CentOS7 rather then CentOS6.
