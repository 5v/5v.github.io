---
layout: post
title: "Using Alt in iTerm2"
date: 2015-09-13 20:32:00 +01:00
categories: osx
tags: iterm iterm2 emacs bash
---
The default behaviour of `Alt` in iTerm2 is not as one might expect in `bash` or
`emacs` and prints various characters instead of skipping words *etc.* I prefer
the latter, so need to make a change to the profile in use:

1. Preferences -> Profiles -> Keys tab
2. Change "Left|Right option key acts as: " to "+Esc"

[Reference](http://stackoverflow.com/questions/18923765/bash-keyboard-shortcuts-in-iterm-like-altd-and-altf).
