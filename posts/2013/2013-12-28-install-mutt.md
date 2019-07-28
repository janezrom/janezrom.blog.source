---
title:  Install mutt
date:   2013-12-28
author: Janez Rom
tags:   mutt, mail
---

# mutt

    yaourt -S mutt muttprint abook msmtp offlineimap notmuch notmuch-mutt links

# offlineimap

Use oginal configuration and adapt

    cp /usr/share/offlineimap/offlineimap.conf ~/.offlineimaprc

Run offlineimap with systemd

    vim /etc/systemd/system/offlineimap@.service

and put in

    [Unit]
    Description=Start offlineimap as a daemon
    Requires=network.target
    After=network.target

    [Service]
    User=%i
    ExecStart=/usr/bin/offlineimap
    KillSignal=SIGUSR2
    Restart=always

    [Install]
    WantedBy=multi-user.target

Start systemd where you must replac user_name by your’s user name

    systemctl enable offlineimap@user_name.service
    systemctl start offlineimap@user_name.service


