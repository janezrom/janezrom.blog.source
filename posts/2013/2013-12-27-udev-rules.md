---
title:  Udev rules
date:   2013-12-28
author: Janez Rom
tags:   udev, rules
---

# Reference

[http://reactivated.net/writing_udev_rules.html](http://reactivated.net/writing_udev_rules.html)

# Polar Data link

Edit/create

    /etc/udev/rules.d/99-hid.rules

and put in

    # Polar Datalink
    # /etc/udev/rules.d/99-hid.rules

    # hidapi/libusb
    SUBSYSTEMS=="usb", ATTRS{idVendor}=="0da4", ATTRS{idProduct}=="0004", GROUP="users", MODE="0666"

    # hidapi/hidraw
    KERNEL=="hidraw*", ATTRS{busnum}=="1", ATTRS{idVendor}=="0da4", ATTRS{idProduct}=="0004", MODE="0666"

Reload rules with

    sudo udevadm control --reload-rules
