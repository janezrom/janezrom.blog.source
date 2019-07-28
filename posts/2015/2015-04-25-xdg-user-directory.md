---
title: User specific directories
date: 2015-04-25
author: Janez Rom
tags: linux, user directories, xdg
---

# Change default directorys

# Install

    yaourt -S xdg-user-dirs

Change globaly

    sudo vim /etc/xdg/user-dirs.defaults

or localy

    vim ~/.config/user-dirs.dirs

and put in

    # This file is written by xdg-user-dirs-update
    # If you want to change or add directories, just edit the line you're
    # interested in. All local changes will be retained on the next run
    # Format is XDG_xxx_DIR="$HOME/yyy", where yyy is a shell-escaped
    # homedir-relative path, or XDG_xxx_DIR="/yyy", where /yyy is an
    # absolute path. No other format is supported.
    #
    XDG_DESKTOP_DIR="$HOME/desktop"
    XDG_DOWNLOAD_DIR="$HOME/downloads"
    XDG_TEMPLATES_DIR="$HOME/templates"
    XDG_PUBLICSHARE_DIR="$HOME/public"
    XDG_DOCUMENTS_DIR="$HOME/documents"
    XDG_MUSIC_DIR="$HOME/music"
    XDG_PICTURES_DIR="$HOME/pictures"
    XDG_VIDEOS_DIR="$HOME/videos"

and update running

    /usr/bin/xdg-user-dirs-update --force

