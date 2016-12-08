---
title: "Stop Windows host intercepting Super+L in VirtualBox guest"
date: 2014-04-20 17:07:09 +01:00
categories: windows
tags:  virtualbox
---
I use tiling window managers in Linux quite often. On a physical machine, I
typically use [Super][] (the "Windows key") as the modifier for the window
manager I am using (current favourite: [i3][]). To switch between or move
windows, I usually use a combination of `Super + h,j,k,l` or `Super + Shift +
h,j,k,l`. The issue with this in VirtualBox is that a Windows host will capture
`Super+L` and, rather irritatingly, lock the screen.

A quick search solved this issue for me, courtesy of [techie007 on
superuser.com][superuser-techie007]. More or less.

  > Open up regedit.exe through the start menu search box, and then browse down
  > to the following key, creating it if it doesn’t exist:
  >
  > `HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Policies\System`
  >
  > On the right-hand side, create a new DWORD 32-bit value named
  > `DisableLockWorkstation` and give it one of these values:
  >
  > * 1 – Disable Lock Workstation
  > * 0 – Enable Lock Workstation
  >
  > The changes should be immediate, no need to restart anything.

I would have preferred it when `Super+L` still worked in the host OS, with it
being passed through to the guest when it has focus, but this is better than
nothing.

### Update
I didn’t realise at the time, but it turns out that this completely disables
screenlocking, and not just the keybind. Bummer. Still, it will do for now.

[i3]: http://i3wm.org/
[super]: http://en.wikipedia.org/wiki/Super_key_(keyboard_button)
[superuser-techie007]: http://superuser.com/questions/121787/disable-windows-key-hotkeys-when-using-virtualbox
