---
title:  Install Hakyll
date:   2018-04-27
author: Janez Rom
tags:   find
---

# Install hakyll

```
stack install happy alex
stack install pandoc
stack install hakyll
```

# Create blog

    hakyll-init janezrom.github.io
    cd janez.rom.github.io
    stack init
    stack build

# Compile blog

    stack exec site build
    stack exec site watch

# macOS

## Suppress '-nopie' warnings with stack buildon

```
clang: warning: argument unused during compilation: '-nopie'
 [-Wunused-command-line-argument]
```

This warning is shown when compiler support of `-no-pie` is expected but unavailable. It's possible to bypass the warning for a specific version of GHC by modifying a global setting:

```
# ~/.stack/programs/x86_64-osx/ghc-8.2.2/lib/ghc-8.2.2/settings
-- ("C compiler supports -no-pie", "YES"),
++ ("C compiler supports -no-pie", "NO"),
```

## Library warning

```
ld: warning: directory not found for option '-L/usr/local/opt/llvm/lib'
```

Install llvm!

# stack.yaml

```
resolver: lts-12.26

packages:
- .

ghc-options: 
	# All packages
	"$locals": -Wall
	"$targets": -Werror
	"$everything": -O2 -dynamic
	# some-package: -DSOME_CPP_FLAG
```





