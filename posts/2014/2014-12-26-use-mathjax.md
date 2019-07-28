---
title:  Configure and use MathJax
date:   2014-12-26
author: Janez Rom
tags:   linux, mathjax, static blog
---

# Test

I’ve recently become interested in starting a blog for various reasons. Since I have jumped head-first into the Haskell programming world, I decided to use a static site generator written in Haskell. The best one out there, of course, is Hakyll.

At the core of Hakyll is the wonderful Pandoc library by John MacFarlane. Pandoc can convert documents between different formats, including Markdown, reStructuredText, and HTML, among many others (check out the graph on the front page of Pandoc’s site). With the power of Pandoc, Hakyll allows you to write the content of your website in a readable markup language, like Markdown or reStructuredText, and convert it to HTML.

and code $$ a_2 = \sin(x) $$ in

V tekstu pa napisem $a_2=\sin(x)$.

$$ \ln{x} = \int _{-\infty} ^ x \frac 1 y \, dy  $$


```bash
#!/bin/sh
# http://christoph-polcin.com/

TMP=/tmp

[ $# -lt 1 ] && \
    echo "usage: $(basename $0) input_file [output.pdf]" && \
    exit 1
```

some text

```python
# Import the modules
import sys
import random

ans = True

while ans:
    question = raw_input("Ask the magic 8 ball a question: (press enter to quit) ")

    answers = random.randint(1,8)

    if question == "":
        sys.exit()

    elif answers == 1:
        print "It is certain"
```


```c
#include <unistd.h>
#include <stdio.h>

// If g++ still gives error Try using:
// g++ file.c -lstdc++

int main() {

    char *name;
    name = getlogin();
    if (!name)
        perror("getlogin() error");
    else
        printf("This is the login info: %s\n", name);
    return 0;

}
```


That is all.
