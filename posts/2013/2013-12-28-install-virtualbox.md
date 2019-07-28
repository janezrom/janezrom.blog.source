---
title:  Install virtualbox
date:   2013-12-28
author: Janez Rom
tags:   virtual box, install
---

# virtualbox

    yaourt -S virtualbox virtualbox-guest-modules virtualbox-host-modules virtual-guest-tools

# virtualbox-extension-pack

You must load vboxdrv module before starting VirtualBox

    groupadd vboxusers
    gpasswd -a username vboxusers

Automatic module startup

    tee -a /etc/modules-load.d/virtualbox.conf <<< "vboxdrv"

# Manual modules startup

    modprobe vboxdrv

Download extension-pack from https://www.virtualbox.org/wiki/Downloads

    virtualbox-extension-pack

# VBOX crashing during guest OS boot after update

Generally updates involving kernel upgrades hit extensions/addons and mostly becomes reason for problem.

    uname -r && pacman -Q | grep virtual

This revealed extensions pack has different version than all other virtualbox packages.

This may not be the best and other solutions may exist, but I used following steps.

1. Removing problem maker

2. sudo pacman -R virtualbox-extension-pack

3. Disable USB 2 support from VM settings (otherwise you will get error while trying to run VM)

4. Run VM to make sure it works.

5. Re-installing extension pack.

6. Enabled USB 2 support for VM from settings > USB.

# Install guest modules

    pacman -S virtualbox-guest-dkms virtualbox-guest-iso

    pacman -S linux-headers

    sudo  dkms install vboxguest/4.3.18


