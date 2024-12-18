---
layout: page
title: Slackware 12, a Review
cover: 'assets/images/cover1.jpg'
navigation: true
logo: 'assets/images/ghost.png'
current: publications
---


![](/assets/images/2017/03/slackware_traditional_website_logo.png)

__Author: Michiel van Wessem__ <br />
__Article orginally published: 2007[¹]__

Well, it has been that time again and Patrick has released a new version of our most favourite Operating System, and I am sure that everyone who has been awake the last couple of days has noticed this. So what has changed between versions 11.0 and the newest flagship 12.0? 

A lot, actually. Lets have a look on both the outside and inside to see what has changed.

Undoubtedly, the major changes are clear: A new toolchain (containing a new glibc and a  new gcc), a modular Xorg, new XFCE  (4.4.1) and the latest KDE-3.5.7, not to forget DBUS and HAL automounting for desktop users. , and above all the first Slackware to be completely 2.6. There are many other changes as well, a lot of them are already highlighted by Patrick himself in his official announcement, and by Robby Workman in his `CHANGES_AND_HINTS.TXT`. 

Lets have a little bit of an overview of what is new and changed:

**The Kernel:**

But lets start at the heart of any Linux distro, the kernel. With 12.0 Slackware has moved out of the 2.4 range and gone to be a solemnly a 2.6 kernel affair only. Slackware now comes with 4 separate kernels. Standard are the 2.6.21.5 kernel, which was also the latest (at time of writing, .6 just came out before I could finish this article) stable kernel being offered at kernel.org. 

The standard kernel used during the install is the huge-smp kernel. There are two huge-* and two generic-* kernels in Slackware. The huge-* kernels have almost every driver in the kernel built in, which makes em ideal for use during the installation. The generic-* kernels offer the same amount of hardware support, however the biggest difference is that unlike the -huge kernel, is that in the -generic mostly everything is compiled as a module. Using the generic kernel will mean you need to build an initrd. Luckily with help of the README.initrd, mkinitrd(8) and mkinitrd --help it's not all that hard to figure out.

There maybe however some software (such as the NVIDIA drivers) that requires your system to be configured as completely non-smp. For that purpose Patrick has included a linux-2.6.21.5-nosmp-sdk. This will patch several kernel-headers as well as the standard kernel config.

**Other Changes**

One of the bigger (and under the hood) changes of Slackware is the new toolchain. This includes a new glibc (upgraded to version 2.5), new binutils and a new gcc compiler (upgraded to gcc4.1.2). Another big change in Slackware is the addition of HAL (Hardware Abstraction Layer) and DBUS. This makes automounting of CDs, digital cameras and USB devices a breeze. Insert, click about a bit, and voilà: instant access to your information.

The two other big changes are of course that both modular Xorg (Xorg 7.2 is included as the standard Xserver) and KDE-3.5.7 are compiled to be both installed into /usr to fit better in line with the freedesktop.org recommendations for unifying the various Linux desktops. The added bonus is that the more centralised use of /usr will actually make building third-party packages a lot easier to deal with in the future.

As for the network services, things have been improved as well. The old tcp/ip package has now been split into number of smaller packages, each containing their own specific utilities. From a maintenance point-of-view, this makes certainly sense. It will be a lot easier for Patrick and the Crew to maintain the different utilities instead of reminding themselves how to build the bigger tcpip packages.

Another one of the bigger changes in Slackware 12.0 is the dropped support for the old and trusty apache webserver, which is being replaced by httpd. When this was first announced in the ChangeLog.txt, it caused a bit of confusion. Basically, httpd is what is generally called apache2, just using the official name the Apache Project has given their webserver.

Other new things include the support for Bluetooth in the shape of the bluez utility set. Also automatic support for Network Time Protocol has been added. New in this version is support for SNMP. This is especially useful for when being used in a server environment or for example with an UPS.  It's perhaps a tiny improvement but all in all it gives Slackware that extra shiny glossy finished feel.

Perhaps one of the more surprising steps was the inclusion of the traditional SystemV init directories. Before now, these needed to be added by the user if (or when) they were needed (for example: when installing WMWare or Xen on Slackware). I think this has always caused confusion for a lot of people, but in short it comes down to this: Slackware is a SystemV system that uses BSD Style Scripts (Style being the operative word here). The clue as to why, is twofold. The first is that in a SystemV init system, the /etc/inittab is being used (as does Slackware). Secondly, if you have a look through the startup scripts, rc.sysvinit is called for every runlevel change, startup or stopping of the machine. Still Slackware's way of dealing with it's startup script is (at least in my opinion) much cleaner than the the more traditional SystemV init system and better than BSD handles it (but then again, that is probably not a great surprise).

In version 12.0, the `magic SysRQ` key in the kernel is enabled by default. The SysRQ key is a way to communicate with the kernel on a very low level without interfering with or by anything else. Basically it allows for 'magical' key combos you can hit which the kernel will respond to regardless of whatever else it is doing, unless it is completely locked up. One Example is:

	"Raising Skinny Elephants Is Utterly Boring"

The above statement stands for the keys to be pressed in order to reboot a completely locked machine. The meaning is in the first letters of each word: (R)aw keyboard mode (S)ync the disk t(E)rminate the processes k(I)ll all processes remo(U)nt all file systems read only and finally re(B)oot the system.

One of the additions which will benefit a lot of people who use KDE and KMail is the integration of full encryption in KMail. Before 12.0 it was possible to actually sign and encrypt mails and understand who signed emails. However decrypting emails was not possible (at least not on the fly). However, now with the added libraries and tooling, KMail has no longer any problem dealing with encrypted emails.

One thing I almost forgot to touch upon more deeply (although I mentioned it very briefly before) is the inclusion of DBus and HAL from freedesktop.org. Dbus offers a simple way for applications to communicate with each other. HAL, short for Hardware Abstraction Layer, offers a way for desktop applications from, for example, KDE and XFCE to readily access the hardware information so that they can locate and use such hardware regardless of bus or device type. This will make it much much easier for users to have direct and quick access to their hardware including features such as automounting. With HAL enabled, you no longer need to have lines for your cd/dvd or usb device in your /etc/fstab. HAL will detect the device and automatically make it available.

The biggest caveat with HAL is that you *have* to add your users to the plugdev group. This [posting by Robby Workman on Linuxquestions.org](http://www.linuxquestions.org/questions/showthread.php?t=566862) explains exactly why and what the issue is.


**The Installation**

The installer itself hasn't changed much. Other than that the installer is still the same in looks as we've always seen in Slackware. It works well and it's trusted. I have played in the past with other installers and none are as clean, quick and easy to understand as the Slackware installer. (Even my girlfriend can install Slackware ;) )

One of the things that has been removed from Slackware is the old floppy disk install. Even though this has been part of Slackware since the beginning of time (or rather the beginning of Slackware), it has now been dropped in favour of either a USB or a PXE (think netbooting) install.  In that same fashion, the "create bootdisk has been replaced by a USB-variant. 

The installer has now support for both LVM as well as encrypted partitions (using cryptsetup aka dm-crypt). Both are well documented by README_CRYPT.TXT and README_LVM.TXT by the hand of Eric Hameleers (aka AlienBOB). Having tried the cryptsetup on my laptop, it worked flawlessly (apart from a slight PEBKAC). Please note that there is a small addition  to the way that the setup uses encrypted partitions and lilo. These [extra notes](http://alien.slackbook.org/dokuwiki/doku.php?id=Slackware:setup) have been published on alien's wiki.



**Upgrading from a previous installation**


Upgrading is as per usual with Slackware still a viable option. However due to the many changes in Slackware (such as Xorg and KDE, more about that later), anyone wanting to follow the upgrade path best carefully follow and read the UPGRADE_AND_CHANGES.TXT. Robby Workman has put in a lot of work detailing everything that needs to be done for a seamless upgrade. Please Do not forget to run <b>lilo</b> afterwards.

Also note that non-empty directories will not be removed by the pkgtools (removepkg(8) / upgradepkg(8)). So after the installation, you may have some old directories lying around (/etc/hotplug and /etc/apache come to mind). So have a good look through your /etc/ directory when you are done upgrading. (I suggest making sure you have a backup of /etc/ before you remove anything. But we all make regular backups, right?)

One of the things to easily forget is to either run lilo afterwards, or to merge all the new files. Especially the new files *must* be merged before hand, otherwise a lot of strange things might happen or just plain not work. The best way I have found to do it is to just keep running <b>find /etc/ -name "*.new"</b> until that search runs out of any results that it can find. Having done a couple of upgrades (somewhere around four to six times), as long as you strictly follow the UPGRADE_AND_CHANGES.TXT you really can't go wrong.

One note of warning: If for some reason you are relying on external tools such as slapt-get and swaret, you *will* run into problems. Those tools have no idea of how to do upgrades and basically will upgrade things in an alphabetic order. This means that things like bash get upgraded before the glib-solibs package. As bash in Slackware-12.0 is linked against this, you will see enormous problems. (basically all will stop working). Take my advice, don't use these tools. No seriously, just don't. However if you are have managed to muck up your install in this way, not all is lost yet. Robby Workman has written a [document on how to repair/rescue your system](http://rlworkman.net/howtos/glibc-recovery). On that note, if you feel the need to have a bit of the upgrade process done automagickly, I can recommend slackpkg. Slackpkg is written by PiterPunk and supports upgrading from 11.0 to 12.0 as long as you follow the manpage.


**How to get slackware**


There are a couple of ways to get your hands on Slackware. The best way of course is to buy the disk from the Slackware store. That way you do something good, support the project financially and get a fancy set of CDs (or the DVD) to put on your bookshelf. 

You can also of course download Slackware from the mirrors. You can find a [list of mirrors](http://slackware.com/getslack/) either here on *[alphageek's website](http://alphageek.dyndns.org/linux/slackware-mirrors.shtml)*. However instead of downloading the ISOs straight from a mirror, the preferred way is to use the torrents. Slackware.com puts their releases out there as torrents for the 6 CDs and the DVD. So the more people use the torrents the more and better the speed will be.

One other way will be to use rsync(8) and sync the full mirrors onto your local harddrive (disk2disk install or upgrades are lightning fast). But once you have the mirror synced completely, you could use [sligdo](http://alphageek.dyndns.org/linux/sligdo/) to create your own ISOs rather quickly (these will be mirrors that are a 100% compatible with the ISOs offered by the torrents).

If you just want the binaries you just need the first couple of CDs. Disc1 contains A/, AP/, D/, E/, F/, K/, L, /, N/, TCL/, Y Series. All you need to get a basic system ready to run. The only things you will be missing out on is anything related to the X-series. But if you want to go for a lean server install this is all you need. For those who want a bit more, they want to download Disc2 which contains the KDE/, T/, X/, XAP, and most of /extra, as well as the /usb-and-pxe-installers. Disc3 contains KDEI/ which you really only need if you want some extra language support, and even then, it may be a lot quicker just to download the kde-i18n-* and the koffice-l10n-* for your own language. Of course the choice is yours. CDs 4-6 are the source CD's and contains all the sources that were used to create Slackware. If you download the DVD you get of course everything, including a copy of The Revised Slackware Book aka "The Good Book" or "Slackware Linux Essentials".



**Repositories**

If you want extra packages for Slackware, or you are just missing that special package, there are a few places on the Internet that I recommend. Of course the first one will be SlackBuilds.org (yes, I am probably biased).  The team over at SlackBuilds.org have worked hard during the last month to get their whole archive converted and tested to confirm that they work on 12.0 before Slackware was released.

However if SlackBuilds.org don't have the scripts for that package that you need, have either a look at [AlienBOB's repository](ttp://www.slackware.com/~alien/slackbuilds/) over at or have a look at [Robby Workman's](http://rlworkman.net/pkgs/). Alternatively you could compile it from source using one of the many tools that Slackware gives you (makepkg(8), or slacktrack(8)). Of course if you feel really up for it, create a SlackBuild script (see how on http://slackbuilds.org/guidelines/) and submit it. The more applications we have in our repository the better.

If you really have a desperate need to use precompiled packages, the only site I can recommend is slacky.eu[²]. (formerly known as slacky.it). They also provide the Slackbuild script and the source with each package, so you can still compile your own.



**Community and Support**


Slackware has one of the best communities I have come across. As long as you are willing to put in a little bit of work, people are generally willing to help you out. Sure we might expect from you that you read the manpages after we have pointed them out, that you know what you generally are doing, that you actually can do some rudimentary googling. I always found [this page](ttp://mikeash.com/getting_answers.html) a good link on helping and getting help for your problems.

There are two good irc channels available for your support, ##Slackware on irc.freenode.net and #Slackware on irc.oftc.net. Also, there is the Slackware forum over at [linuxquestions.org](http://www.linuxquestions.org/questions/forumdisplay.php?f=14). Of course once you have slackware up and running it certainly wouldn't hurt to at least sign up for the Slackware mailing list, so you'll be kept up to the date when there is a vulnerability out and Patrick has provided a patch or an update for the package.



**Conclusion**


If you want to run Slackware as a server, it is more than up for the task, not only do you get a stable platform, you also get loads of services by default; Bind, httpd (apache2), MySQL, PHP (so you are already setup for a LAMP machine if you wished so), Sendmail/getmail/procmail/IMAP, vsftp and proftd (FTP server), Samba, a DHCP Daemon, a NTPD aemon and Secure Shell Access. So pretty much whatever you want. There are some services Slackware doesn't yet provide (I am thinking of things like single sign-on services and things that may depend on PAM) 

On the other hand if you want Slackware as a desktop it is more than up to the task with this latest version. A very good looking XFCE and of course the latest version of the KDE Desktop Environment. And for the applications? I could name every application that I think is worth mentioning, but it will be come an endless list of what is good and what is better. Besides if you have read the CHANGES_AND_HINTS.TXT and the RELEASE_NOTES and [Patrick's official Announcement](http://slackware.com/announce/12.0.php) you will have noticed most of the new stuff already. Suffice to say that Slackware delivers at least a very complete set of applications to do your daily work. I can easily do a lot of work without having anything extra installed.

I can't conclude any different than simply stating the fact that with Slackware 12.0, Patrick has delivered an outstanding piece of work, which just simply and clearly outshines any of the previous versions of Slackware. I have debated doing a scoreboard for the various parts in Slackware, but I realised at the end of it it was going to be useless as I would rate everything high regardless. The biggest problem I faced when writing this article is that I found myself starting to sound like a broken record. This is better, This is good, This has improved... 


and to be honest on that bombshell...


Yes, Slackware 12.0 is simply THAT good!.


<br><br>
[¹]: This article appeared on Sunday, Jul 8, 2007 on "The Slack World", an online e-zine, focusing on the slackware distribution. The article is archived here; as is. 
[²]: This was at the time of writing in 2007. Currently I believe the site switched to gnome based desktops, rather then clean standard installations of Slackware.
