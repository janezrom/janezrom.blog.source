---
title:  Install applications
date:   2013-12-28
author: Janez Rom
tags:   applications, install
---

# Basic applications

    pacman -S mc gvim
    packer -S ranger rxvt-unicode
    pacman -S zip unzip p7zip arj unarj atool

    pacman -S firefox thunderbird

Change font size of firefox developper window

    cd /home/<user>/.mozilla/firefox/<default-pr0file>

    mkdir chrome
    cd chrome

    vim userChrome.css

and put in

    @namespace url(http://www.w3.org/1999/xhtml);
    @-moz-document regexp("chrome://browser/content/devtools/.*") {
        * { font-size: 20px !important }
    }

    pacman -S libreoffice
    pacman -S texlive-most texlive-lang lyx

    pacman -S alsa-lib alsa-tools alsa-utils alsa-plugins

Alsa applications are `alsamixer` and `alsactl store`

# Aditional applications

    pacman -S flashplugin

    pacman -S mpd ncmpcpp
    pacman -S clang git

    pacman -S cclive
    # Other youtube applications: movgrab youtube-dl minitube

    pacman -S gparted gksu dosfstools ntfsprogs gpart mtools

Run with “gksu gparted”

    pacman -S k3b

Show k3b dependencies

    pacman -Qi k3b
    pacman -S dvd+rw-tools vcdimager transcode emovix cdrdao

    pacman -S transmission-qt

    pacman -S mariadb

    pacman -S gimp darktable feh imagemagick
    pacman -S devede mencoder gstreamer0.10-plugins mutagen
    pacman -S dos2unix

    pacman -S geogebra
    pacman -S sage-mathematics

    yaourt -S opencascade

Make bigger tmpfs

    nano /etc/fstab # tmpfs = 1/2 RAM

by

    tmpfs /tmp tmpfs nodev,nosuid,size=4G 0 0

to be ble to compile opencscade.

    yaourt -S elmer
    yaourt -S freecad

# Skype

    nano /etc/pacman.conf

Find and uncomment 2 multilib lines

    [multilib]
    Include = /etc/pacman.d/mirrorlist

and run

    pacman -Syu
    yaourt -S skype lib32-v4l-utils

# Light browsers

    yaourt -S jumanji-git webkitgtk3
    yaourt -S dwb-gtk3-git
    yaourt -S uzbl-git

# Light pdf viewer

    yaourt -S mupdf zathura

Optional dependencies for zathura zathura-djvu zathura-pdf-poppler zathura-pdf-mupdf zathura-ps

# Developpement

    yaourt -S kdevelop codeblocks

# Mapping tools

    yaourt -S freeplane

# Raytracers

    yaourt -S povray yafaray pixie luxrender aqsis sunflow radiance

# Video

    yaourt -S avidemux-gtk

# CLI spreadsheet applications

    sc slsc vim-orgmode Spreadsheet.vim oleo

# Security

Security scanner, zenmap (gui)

    pacman -S nmap zenmap

# Ideas

tig - Curses based git repo browser. I mainly use the command line but this is handy for browsing a repo. hub is a command-line wrapper for git that makes you better at GitHub.

winff - WinFF is a GUI for the command line video converter, FFMPEG.

aur/sndfile-tools spectrogram : sndfile-spectrogram “05 - A Love Supreme.flac” 800 800 spec.png spec

duply is a frontend for the mighty duplicity

https://github.com/dotphiles/dotphiles

# arch wiki offline

    pacman -S arch-wiki-docs

# spell

yaourt -S vim-spell-en vim-spell-sl vim-spell-fr yaourt -S aspell-en aspell-sl aspell-fr

# ebook

    pacman -S lucidor

coolreader = cr3
