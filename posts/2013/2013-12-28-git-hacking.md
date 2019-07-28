---
title:  Git hacking
date:   2013-12-28
author: Janez Rom
tags:   git
---

# Install git and fgit viewers

    yaourt -S git tig

# Initialise

Create a new repository on the command line

    touch README.md
    git init
    git add README.md
    git add ..file and directory
    git commit -m "first commit"
    git remote add origin https://github.com/janezrom/janezrom.github.io.git
    git push -u origin master

# Add new files and push new commit

    git add -A
    git commit -m "new commit"
    git push -u origin master

# Reduce size of git directory

    for dir in /home/janez/.vim/bundle/*; do (cd "$dir" &&  git gc --aggressive --prune=now); done


