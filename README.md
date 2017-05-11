crouton-fedora-wayland: Crouton version for Fedora
=================================================

This is a modified version of Crouton which installs Fedora onto your Chromebook.
This version isn't nearly as polished as the main version of Crouton with Debian/Ubuntu.
Please don't use this if you aren't familiar with the Crouton project as it is much better
than this version. This specific version ditches the old X server with Freon idea, and uses
Wayland which is built-in in the latest couple of versions of Chrome OS. It is much simpler
and actually faster.

Disclaimer
=================================================

All the work here is based on the official Crouton version which can be found here:

https://github.com/dnschneid/crouton

and on this (now a bit old, but still fantastic source) fork for Fedora 20:

https://github.com/divx118/crouton/tree/fedora

I am eternally grateful for these versions, and all the credits should go to their authors.
I merely played with them and modified them a bit.

Original Crouton Fedora:

https://github.com/nmilosev/crouton-fedora

Useful links
=================================================

My original blog post about crouton-fedora:

http://nmilosev.svbtle.com/crouton-with-fedora-chroot-chromebook

The version 2.0:

http://nmilosev.svbtle.com/crouton-with-fedora-chroot-2-0

The Crouton Fedora chrome app and VNC instructions:

http://nmilosev.svbtle.com/fedora-crouton-connector-chrome-app

Installing VirtualBox:

https://nmilosev.svbtle.com/virtualbox-and-crouton-fedora

Running Docker:

https://nmilosev.svbtle.com/docker-on-crouton-fedora-24

Crouton + Fedora + Wayland = YES.:

https://nmilosev.svbtle.com/TBA

A word of warning
=================================================

If you want maximum stability, please use official Crouton and install Debian or Ubuntu.
This may break with an update or might not even work at all. Things may break at anytime. 
This needs a lot more work. You have been warned.

Installation
=================================================

1. Developer unlock your chromebook
2. Open crosh shell

```
cd ~/Downloads
wget https://github.com/nmilosev/crouton-fedora-wayland/archive/master.tar.gz -O crouton-fedora-wayland.tar.gz
tar xvf crouton-fedora-wayland.tar.gz && rm crouton-fedora-wayland.tar.gz
sudo sh ./crouton-fedora-wayland-master/installer/main.sh -r fedora -t fedora
```

This installs the CLI version and support for Wayland. 

To enter Fedora: ```sudo enter-chroot```

A good practice is to also include a parameter ```-p``` to install this Crouton to the non-default path
since it breaks the official Crouton if you have it installed. For example:

```
sudo mkdir /usr/local/crouton-fedora
sudo sh ./crouton-fedora-master/installer/main.sh -r fedora -t fedora -p /usr/local/crouton-fedora
sudo sh /usr/local/crouton-fedora/bin/enter-chroot
```

Please consult the offical Crouton documentation for this.

With this paramter, you can also install Crouton Fedora onto your sd card or your USB drive. Just please
remember, that performace will be greatly reduced if your SD card/USB drive is slow.

Wayland
---

Wayland support is built in directly. If you only want CLI you have to modify the installation files or use
the old version. Search for "# Wayland support:" comment!

FAQ:
---

**How much space do I need?**

- ~3GB for the GNOME + CLI installation.
- ~2GB for the XFCE + CLI installation.
- ~500MB for CLI only.

**My download is slow or not working...**

Modify the ```defaults``` file in ```installer/fedora``` folder. You can find mirrors on the
fedora mirror list site.

**What about Wine?**

Wine works fine. I've sucessfully installed Photoshop CS6 through the PlayOnLinux Wine front-end.

**Virtual Box/Docker?**

Both work. Check the useful links section.

License
-------
crouton (including this eloquently-written README) is copyright &copy; 2016 The
crouton Authors. All rights reserved. Use of the source code included here is
governed by a BSD-style license that can be found in the LICENSE file in the
source tree.

Fedora is property of Red Hat Corporation.

I'm merely a mortal, if anybody is offended by this code, please inform me, and it
will be taken down immediately.
