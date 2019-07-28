---
title: Install android support
date:   2013-12-28
author: Janez Rom
tags:   android
---

# Android support

    packer -S heimdall-git

    packer -S android-udev
    gpasswd -a USERNAME adbusers
    cp /usr/lib/udev/rules.d/51-android.rules /etc/udev/rules.d
    udevadm control --reload-rules

    packer -S android-sdk
    packer -S android-sdk-platform-tools

    chown -R janez /opt/android-sdk
    groupadd android
    gpasswd -a USER android

    chgrp -R android /opt/android-sdk
    chmod -R g+w /opt/android-sdk
    find /opt/android-sdk -type d -exec chmod g+s {} \;

Change in

    vim ~/.bashrc

path

    PATH=$PATH:/opt/android-sdk/platform-tools

# Define rules

    vim /etc/udev/rules.d/51-android.rules

Put in

    # Galaxy S5
    SUBSYSTEM=="usb", ATTR{idVendor}=="04e8", ATTR{idProduct}=="6860", MODE="0666"
    SUBSYSTEM=="usb", ATTR{idVendor}=="04e8", ATTR{idProduct}=="6860", SYMLINK+="android_adb"
    SUBSYSTEM=="usb", ATTR{idVendor}=="04e8", ATTR{idProduct}=="6860", SYMLINK+="android_fastboot"
    SUBSYSTEM=="usb", ATTR{idVendor}=="04e8", ATTR{idProduct}=="6860", SYMLINK+="libmtp-%k", ENV{ID_MTP_DEVICE}="1", ENV{ID_MEDIA_PLAYER}="1"

and apply rules

    udevadm control --reload-rules

# Other commands

    pacman -S mtpfs libmtp

Detect device

    mtp-detect

Connect MTP device

    mtp-connect

Configuration

    groupadd fuse
    gpasswd -a USER fuse

or

    vim /etc/group -> add USER to fuse

and uncomment

    vim /etc/fuse.conf
    user_allow_other

continue

    sudo mkdir /mnt/MOUNTPOINT
    sudo chown janez /mnt/MOUNTPOINT

mount your device

    mtpfs -o allow_other /media/YOURMOUNTPOINT

unmount your device

    umount /media/YOURMOUNTPOINT

Put into ~/.bashrc -> note = Samsung Galaxy Note

    alias mnote="mtpfs -o allow_other /media/YOURMOUNTPOINT"
    alias unote="sudo umount /media/YOURMOUNTPOINT"

    pacman -S libmtp
