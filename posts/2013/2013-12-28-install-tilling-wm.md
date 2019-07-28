---
title:  Install tilling window managers
date:   2013-12-28
author: Janez Rom
tags:   window manager, tilling
---

# Start tilling window manager

## With .xinit - terminal login

Edit .xinitrc file

    vim ~/.xinitrc

and put in

    if [ -d /etc/X11/xinit/xinitrc.d ]; then
        for f in /etc/X11/xinit/xinitrc.d/*; do
            [ -x "$f" ] && . "$f"
        done
        unset f
    fi

    # set cursor
    xsetroot -cursor_name left_ptr

    # set background
    xsetroot -solid '#090909' &

    # set background
    #feh --bg-scale ~/Downloads/arch88e.jpg &

    # Start one of window managers

    #sxhkd & exec bspwm
    ~/.xmonad/xmonad-x86_64-linux
    # herbstclient
    #exec startxfce4

# From kde

I left kde for xfce4 which is lighter. Below configuration is valable for kde 4.

    sudo vim /usr/share/apps/kdm/sessions/herbstluftwm.desktop

and put in

    [Desktop Entry]
    Encoding=UTF-8
    DesktopNames=herbstluftwm
    Name=herbstluftwm
    Comment=This session start herbstluftwm
    Exec=herbstluftwm
    Type=Application

Change respectivly herbstluftwm with program (and location if needed) your tilling window manager.

# bspwm

## Install bspwm and sxhkd

    yaourt -S bspwm-git sxhkd-git

Copy bspwmrc to ~/.config/bspwm/bspwmrc and sxhkdrc to ~/.config/sxhkd/sxhkdrc and make bspwmrc executable with chmod +x ~/.config/bspwm/bspwmrc

# herbstluftwm

## install configuration file

    yaourt -S herbstluftwm-git dmenu dzen2-git

    mkdir -p ~/.config/herbstluftwm
    cp /etc/xdg/herbstluftwm/* ~/.config/herbstluftwm

# windows properties

xprop | grep WM_CLASS

