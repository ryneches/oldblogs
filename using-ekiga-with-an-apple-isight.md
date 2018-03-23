Title: Using Ekiga with an Apple iSight
Date: 2007-04-21 03:14:53
Category: general
Slug: using-ekiga-with-an-apple-isight
Author: Russell Neches
Tags: ekiga, isight, apple, webcam, voip, video, linux, howto
Summary: 


Now that Apple is integrating little video cameras into most of its
products, the venerable Apple iSight has been discontinued. This is very
good news if you happen to know a Mac user who likes to buy new things.
Chances are pretty good that they have an iSight that they no longer
need. Despite being discontinued, the iSight still seems to command its
former full retail price on eBay for reasons I do not understand.
However you get your hands on one, the iSight can be made to work on a
Linux machine without too much difficulty.

The iSight isn't a particularly wonderful video camera, but it is pretty
ideal for videoconferencing. So, here is how to get the iSight to work
with Gnome's videoconferencing software, [Ekiga](http://www.ekiga.org).
I will assume that you know how to find and install software on your
computer.

![](http://vort.org/media/images/ekiga_screenshot.png)

You will need an ieee1394 port, and you will need to load the following
kernel modules :

-   ieee1394
-   video1394
-   ohci1394
-   videodev

You will also need to make sure video4linux (V4L2) and the V4L1
compatibility modules is either loaded as a module of compiled into your
kernel. The easiest way to get the device working is with the
[vloopback](http://www.lavrsen.dk/twiki/bin/view/Motion/VideoFourLinuxLoopbackDevice)
kernel module, which you will probably have to download and build
yourself (I found the Subversion repository to be easiest to use -- the
1.1-rc1 tarball complained of a missing config.h file).

Once you've got the vloopback module loaded, you should be able to get
the camera working using
[Coriander](http://damien.douxchamps.net/ieee1394/coriander/index.php).
When you launch Coriander, it will either work, or it will tell you
which kernel modules you are missing. If it works, you should see "Apple
Computer, Inc." under the "Camera Select" dropdown menu. The Coriander
interface is somewhat counterintuitive and a bit heavy on options, but
it is very useful. Go to "Services" and select "VIDEO1394" from the
"Method" dropdown menu. Then clicking the "Receive" and "Display"
buttons (which are actually toggles, despite appearances) should pop
open a video preview.

Chances are, the permissions on the necessary devices in /dev will be
wrong, so you may have to run Coriander as root. You should make sure
the devices are readable and writable by the "video" group (or whatever
you or your distribution deems appropriate for the group name), and then
add yourself to that group. You will need to the following devices :

    crw-rw---- 1 root video 81,  0 Apr 20 21:57 /dev/video0
    crw-rw---- 1 root video 81,  1 Apr 20 21:57 /dev/video1 
    ... 
    crw-rw-r-- 1 root video 171, 16 Apr 20 21:57 /dev/video1394/0
    crw-rw-r-- 1 root video 171, 17 Apr 20 21:57 /dev/video1394/1 
    ...
    crw-rw---- 1 root video 171, 0 Apr 19 21:38 /dev/raw1394

Evidently, you don't need these:

    crw------- 1 root video 10, 204 Apr 20 21:57 /dev/video/em8300
    crw------- 1 root video 10, 206 Apr 20 21:57 /dev/video/em8300_ma
    crw------- 1 root video 10, 205 Apr 20 21:57 /dev/video/em8300_mv
    crw------- 1 root video 10, 207 Apr 20 21:57 /dev/video/em8300_sp

You may want to use your iSight for something other than uploading
images to an FTP site (which Coriander will do wonderfully). If you try
to use your iSight with [Ekiga](http://www.ekiga.org/), you may notice
that even with all the right kernel modules loaded, it's still
impossible to configure the iSight via the Ekiga configuration druid. If
this is the case, you need to install some packages :

-   libpt-1.10.0 - Portable Windows Library
-   libpt-plugins-alsa - Portable Windows Library Audio Plugin for the
    ALSA Interface
-   libpt-plugins-avc - PWLib Video Plugin for IEEE1394 (FireWire) AVC
    devices
-   libpt-plugins-dc - PWLib Video Plugin for IEEE1394 (Firewire) DC
    Devices
-   libpt-plugins-oss - Portable Windows Library Audio Plugins for the
    OSS Interface
-   libpt-plugins-v4l - Portable Windows Library Video Plugin for
    Video4Linux
-   libpt-plugins-v4l2 - Portable Windows Library Video Plugin for
    Video4Linux v2

Quit Ekiga and try the druid again. You should be able to select
"1394DC" for the Video plugin, and "/dev/video1394/0" for the Input
device. Clicking the little video icon should start the video preview.

**Note:** If you close the little shutter on the iSight while Ekiga is
running, it will crash. Evidently the shutter actually turns off the
device.
