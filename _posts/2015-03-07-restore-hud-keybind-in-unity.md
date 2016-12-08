+++
title = "Restore HUD keybind in Unity"
date = "2015-03-07T00:27:55+01:00"
categories = [ "linux" ]
tags = [ "emacs", "hud", "ubuntu", "unity" ]
+++
Emacs occasionally piques my interest; as a vim user, this could be considered
"odd", but I like to experiment. During my trials, I often inadvertently
triggered display of the HUD when using any `meta` shortcut (which in emacs, is
a lot!). I have subsequently realised that it was my interaction with the
keyboard that was at fault, rather than the HUD triggering when it shouldn't,
hence this post describes disabling the shortcut and then the required steps to
enable it once again.

Disabling the shortcut is simple: fire up System Settings and hit Keyboard. Go
to the Shortcuts tab and in Launchers select the "Key to show the HUD" entry
and hit `<backspace>` to clear the shortcut. Voila, `<Alt>` will no longer
trigger the HUD.

Darn! I quite liked the HUD, so I want to bring it back: I fire up settings,
select the relevent shortcut to edit and hit `<Alt>` - "Disabled," says System
Settings. "Hmmm," I say, "I wonder why that didn't work?" I continue to try
this 14 or 15 times before deciding that it probably isn't going to work and
look for an alternative.

After some searching [\[1\]][1][\[2\]][2], I found that the following can be
used to change the shortcut back to the default of `<Alt>`, using the terminal.

```bash
gsettings set org.compiz.integrated show-hud "['<Alt>']"
```

Done! You may need to close/reopen System Settings to see the change reflected,
however `<Alt>` now correctly triggers the HUD again.

[1]: http://askubuntu.com/questions/17626/how-can-i-restore-default-keyboard-shortcuts
[2]: https://wiki.ubuntu.com/Keybindings
