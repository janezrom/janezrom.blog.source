---
title:  Camera hacking
date:   2013-12-28 
author: Janez Rom
tags:   camera
---

# Installation

Install `libgphoto2` from the official repositories, and optionally `gvfs-gphoto2` for Nautilus integration and `gphoto2` to have a command line interface.

# Permission issues

    groupadd camera
    usermod -G camera user_name

    /usr/lib/libgphoto2/print-camera-list udev-rules version 175 group camera > /etc/udev/rules.d/40-gphoto.rules

    sudo pacman -S gvfs-gphoto2  gvfs-mtp

# Using

Quick Commands

    gphoto2 --list-ports
    gphoto2 --auto-detect
    gphoto2 --summary
    gphoto2 --list-files
    gphoto2 --get-all-files 

For advanced file manipulation, use

    gphoto2 --shell 

# Other frontends

Other frontend applications for libgphoto2

    gphotofs        allow using cameras with any tool
                    able to read from a mounted filesystem.
    darktable
    Digikam
    F-Spot
    Gthumb
    GTKam
