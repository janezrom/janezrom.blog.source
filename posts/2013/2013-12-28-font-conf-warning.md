---
title:  Get rid of font config warning in terminal
date:   2013-12-28
author: Janez Rom
tags:   fonts
---

Move your config from the deprecated location to the new XDG location.

    mv ~/.fonts.conf.d ${XDG_CONFIG_HOME}/fontconfig/fonts.conf
    mv ~/.fonts.conf   ${XDG_CONFIG_HOME}/fontconfig/conf.d

where XDG_CONFIG_HOME is by default $HOME/.config, see [http://standards.freedesktop.org/basedir-spec/basedir-spec-latest.html](http://standards.freedesktop.org/basedir-spec/basedir-spec-latest.html)

and results in:

    mv ~/.fonts.conf.d ~/.config/fontconfig/fonts.conf
    mv ~/.fonts.conf   ~/.config/fontconfig/conf.d

After moving the files, the warning should be gone (at least if you are using fontconfig >= 2.10)
