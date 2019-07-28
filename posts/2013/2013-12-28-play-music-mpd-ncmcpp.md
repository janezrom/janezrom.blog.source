---
title:  Play music - mpd & ncmcpp
date:   2013-12-28
author: Janez Rom
tags:   music, mpd, ncmcpp
---

# mpd

Install mpd (musin player daemon)

    yaourt -S mpd

Create file

    vim /etc/systemd/system/mpd@.service

and put in

    [Unit]
    Description=Music Player Daemon
    After=sound.target

    [Service]
    User=%I
    ExecStart=/usr/bin/mpd %h/.config/mpd/mpd.conf --no-daemon
    ExecStop=/usr/bin/mpd --kill

    [Install]
    WantedBy=multi-user.target

Copy configuration file and change it

    cp /etc/mpd.conf ~/.mpdconf

Enable mpd trought systemd

    systemctl enable mpd@<username>.service
    systemctl start mpd@<username>.service

# ncmcpp

Install ncmcpp (cli music player)

    yaourt -S ncmpcpp

Copy configuration file and change it

    cp /usr/share/doc/ncmpcpp/config ~/.ncmpcpp/config


