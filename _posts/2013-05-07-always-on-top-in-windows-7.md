---
layout: post
title: "Always on top in Windows 7"
date: 2013-05-07 11:13:43 +0100
categories: windows
tags: autohotkey
---

Regularly moving between Linux and Windows naturally highlights the features of
one of them which are missing in the other.

Aside from the obvious differences, there are often little things which one
begins to miss when using "the other" OS. One feature present in almost all
stacking window managers in Linux is the option to toggle a window as "always
on top," yet this facility is not present in Windows (by default). Of course,
there are numerous utilities which can provide this behaviour, but where
possible, I avoid installing software from unknown sources (which many of these
small utilities are).

Enter Autohotkey. Again. The basic functionality I outlined above is achievable
with a [one-liner from Raccoon on the Autohotkey forums][one-liner]:

```ahk
#a:: Winset, AlwaysOnTop, Toggle, A
```

This simply binds the toggling of "always on top" to `super` (Windows key) +
`a`.  There are more complex variants on this, but the above is sufficient for
my needs.

In the future I'd like to add window shading to this script, but for now this
suits me well.

[one-liner]: http://www.autohotkey.com/board/topic/53249-transparent-andor-always-on-top/#entry573906
