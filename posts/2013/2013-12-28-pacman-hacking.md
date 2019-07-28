---
title:  Pacman hacking
date:   2013-12-28
author: Janez Rom
tags:   pacman
---

# Regenerate mirror list

First make safety copy

    cp /etc/pacman.d/mirrorlist /etc/pacman.d/mirrorlist.backup

Optionally run the following sed line to uncomment every mirror

    sed '/^#\S/ s|#||' -i /etc/pacman.d/mirrorlist.backup

# Rank the mirrors

Operand -n 6 means only output the 6 fastest mirrors

    rankmirrors -n 6 /etc/pacman.d/mirrorlist.backup > /etc/pacman.d/mirrorlist


