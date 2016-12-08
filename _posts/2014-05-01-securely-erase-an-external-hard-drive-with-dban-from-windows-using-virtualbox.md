---
layout: post
title: "Securely erase an external hard drive with DBAN from Windows using VirtualBox"
date: 2014-05-01 12:49:08 +01:00
categories: linux windows
tags: dban privacy virtualbox
---
This came up purely because I didn’t want to reboot my PC to securly erase an
external (i.e. non-boot) hard drive. Besides, it would be a waste of a CD-R
anyway.

It’s actually pretty simple if you think it through.

  1.  Download [DBAN][].
  2.  Create a new 32-bit Linux virtual machine in VirtualBox.
  3.  Start said virtual machine, choosing to boot from the DBAN ISO you
      downloaded in step 1.
  4.  When looking at the boot prompt, in the VirtualBox menu bar, go to Devices
      ->USB Devices and choose the device you want to *nuke*.
  5.  Go back to step 4 and *triple check* (minimum) that you have selected the
      correct device.
  6.  Seriously.
  7.  Do it.
  8.  Press `<Return>` at the prompt (after Windows has finished installing the
      VirtualBox USB driver for the umpteenth time) to boot DBAN in interactive
      mode.
  9.  If you're lucky, DBAN will list both the virtual drive of the virtual
      machine you are using in addition to your real, external hard disk [\*](#badluck).
  10. Press space to select the drive you want to wipe and configure any other
      options to your liking.
  11. Press `<F10>` to begin wiping.

That's all there is too it. Works like a charm and saves a reboot!

<a name="#badluck"></a>\* If you were unlucky with step 9, in the VirtualBox menu for this virtual
machine go to Machine -> Settings -> USB and add a device filter for the drive
you want to wipe. Then, reset your DBAN virtual machine and it should
automatically mount, so just continue from step 8.

[DBAN]: http://www.dban.org/
