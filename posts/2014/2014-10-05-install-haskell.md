---
title:  Install haskell
date:   2015-10-5
author: Janez Rom
tags:   linux, install, haskell
---

# Install haskell

    pacman -S ghc cabal-install

Create local directory ~/.ghc and /.cabal by init command

    cabal update

Install local cabal version

    cabal install cabal-install

Uninstall archlinux version of cabal-install

    pacman -R cabal-install

and restart terminal to take in account local version.

# Some useseful applications

    cabal install happy alex

    cabal install xmonad
    cabal install xmonad-contrib

