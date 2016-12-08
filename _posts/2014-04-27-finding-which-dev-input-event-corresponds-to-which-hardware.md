---
title: "Finding which /dev/input/event* corresponds to which hardware"
date: 2014-04-27 17:40:29 +01:00
categories: linux
tags: archlinux hardware
---
I was configuring an Xbox 360 controller in an Arch VM and needed to find out
which input event it was tied to. Saying this now, I have forgotten the reason
why, I just remember that it was a critical piece of information that I needed
to obtain, in order to do *thing*.

A quick bit of [searching][] turns up the `lsinput` command, which it turns out
is from the `input-utils` package. A quick search of the Arch repos yielded
nothing, but a quick search of the AUR turned up the aptly named
[`input-utils`][input-utils] package.  Once installed with ones favourite [AUR
helper][] (currently winning is [`cower`][cower]) it is usable with `lsinput`
(as `root`).

The output is nice and easy to understand, just look for the entry with a
"name" corresponding to what you are looking for.

[searching]: http://askubuntu.com/questions/93016/how-to-identify-relation-between-hid-dev-input-files-and-real-hardware
[input-utils]: https://aur.archlinux.org/packages/input-utils/
[aur helper]: https://wiki.archlinux.org/index.php/AUR_helper
[cower]: https://aur.archlinux.org/packages/cower/
