---
layout: post
cover: 'assets/images/cover-cloud2.jpg'
navigation: True
title: YUM RPM Database corruption on CentOS
date: 2018-01-10 12:47
tags: sysadmin centos technical
subclass: 'post tag-sysadmin tag-centos tag-technical'
logo: 'assets/images/ghost.png'
author: 'michiel'
categories: michiel 
---

&nbsp;

Yum (Yellow Dog Updater, Modified) is a decent package manager for CentOS, and one I have decently gotten to grips with, during my work at my current company (we primairily run CentOS 6 and 7 boxes.

However from time to time you do get the problem that the Yum database becomes corrupted. If this happens you will find something like the following error on your screen:

    [ root@host: ~ ]# yum upgrade -y

    error: rpmdb: BDB0113 Thread/process 1246/139871501219648 failed: BDB1507 Thread died in Berkeley DB library
    error: db5 error(-30973) from dbenv->failchk: BDB0087 DB_RUNRECOVERY: Fatal error, run database recovery
    error: cannot open Packages index using db5 - (-30973)
    error: cannot open Packages database in /var/lib/rpm
    CRITICAL:yum.main:

    Error: rpmdb open failed`

Luckily this is not as disastrous as it would seem. Yum is a rather stable package manager, despite it's metadata database getting itself in a tizzy at the best of time.

So, how do you fix this? First of all we need to remove the old metadata files, and recreate them:

#### Removing the old, corrupted database.

The Yum database is  stored in the below directory:

`cd /var/lib/rpm` <br />

Remove to the files that are causing the corruption. These are only those named __db:

`/bin/mv __db* /tmp`, or if you want to be a little bit more rigorous: `/bin/rm -f __db*`

&nbsp;

#### Rebuild the database

Once this is done, you can rebuild the metadata from scractch using the following commands:


`/bin/rpm --rebuilddb` <br />
`/usr/lib/rpm/rpmdb_verify Packages` <br />
`yum clean all`<br />

You may also want to remove the /var/cache/yum directory, as this may take up free space with data that has now been either orphaned from repositories that you have removed or disabled:

`/bin/rm -rf /var/cache/yum`

The *yum cache* can be rebuild again with the makecache command. The command accepts an extra argument 'fast' that will indeed work faster but does this at the cost of caching fewer repositories.

`yum makecache`, or <br />
`yum makecache fast`

After this, yum should be working again as expected. If you have chosen in the first step to move the database out of the way, you can now remove that as a last clean-up effort.


