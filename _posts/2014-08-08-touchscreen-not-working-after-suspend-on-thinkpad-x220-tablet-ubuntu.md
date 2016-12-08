+++
title = "Touchscreen not working after suspend on ThinkPad X220 Tablet (Ubuntu)"
date = "2014-08-08T20:23:45+01:00"
categories = [ "linux" ]
tags = [ "hardware", "touch", "ubuntu", "wacom", "x220t" ]
+++
For a few releases of Ubuntu, it has been the case that the touchscreen on my
X220 Tablet is non-functional after a suspend. It has never bothered me too
much, but today I decided to have a quick look into the solution.

Thanks to [copper.hat][] on [Launchpad][], the solution is a simple edit that
makes the `wacom` module get unloaded before suspend and reloaded afterwards:

```
vim /usr/lib/pm-utils/defaults
```

Find the `SUSPEND_MODULES` line, then uncomment it and add `wacom`.

```
SUSPEND_MODULES="wacom"
```

Save and exit and after your next suspend, all will be well!

[copper.hat]: https://launchpad.net/~higgins-t
[Launchpad]: https://bugs.launchpad.net/ubuntu/+source/xinput/+bug/1275416/comments/17
