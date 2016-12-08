+++
title = "Installing Windows 7 using EFI from a USB drive"
date = "2014-08-10T20:34:36+01:00"
categories = [ "windows" ]
tags = [ "boot", "efi", "x220t" ]
+++
I fancied installing Windows 7 (64-bit) on the Thinkpad X220T this afternoon,
and came across a stumbling block – the official Windows 7 USB creator does not
allow booting with EFI when installing from a USB stick. I decided that there
must be a solution, and lo, there was.

Thanks to [r3loaded][] on the [bit-tech][] forums a solution was found. For all
the hairy details, see the linked post, but the gist is as follows:

  1.  Format your USB drive (that isn’t made by SanDisk… grr…) to FAT32
  2.  Extract the contents of your LEGAL windows 7 ISO to the root of that USB
      drive (herein `F:`)
  3.  Copy `F:\efi\microsoft\boot to F:\efi\boot`
  4.  Copy `C:\Windows\Boot\EFI\bootmgfw.efi` from an existing Windows 7
      installation (or see the aforementioned post) into
      `F:\efi\boot\bootx64.efi`
  5.  Boot your EFI machine with this shiny new USB drive :)

Note: I specified 64-bit Windows above as I remember reading somewhere that you
can’t EFI boot the 32-bit edition of Windows 7, but I don’t know for sure.

[r3loaded]: http://forums.bit-tech.net/showthread.php?t=209045
[bit-tech]: http://forums.bit-tech.net/
