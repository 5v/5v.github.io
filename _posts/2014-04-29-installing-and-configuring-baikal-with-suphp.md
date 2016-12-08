---
layout: post
title: "Installing and configurating Baikal with suPHP"
date: 2014-04-29 23:15:06 +01:00
categories: linux
tags: apache baikal php
---
[Baikal][] is a CardDAV and CalDAV server written in PHP. I tested it in a
local VM, following the installation instructions in the projects Git
repository and it worked out rather nicely. I did the same thing on my VPS and
naturally, it didn’t want to play ball, spitting out Apache 500 (internal
server) errors and PHP errors such as the following when trying to access it
for the first time:

```apache
[DATE] [error] [client IP] SoftException in Application.cpp:221: File "/path/to/docroot/Core/Frameworks/Baikal/WWWRoot/index.php" is not in document root of Vhost "/path/to/docroot/html"
[DATE] [error] [client IP] Premature end of script headers: index.php
```

Where `DATE` and `IP` are actual dates and IPs.

Now, after some digging it does in fact turn out that it is a problem with the
script it refers to not being in the document root of the noted virtual host.
Who’d have thought it.

The reason it worked in my testing virtual machine is because I was using a
standard LAMP install. On my VPS I use suPHP so any scripts are run as the user
that owns them. Part of the configuration for suPHP is the option:

```ini
check_vhost_docroot=true
```

This will check that any scripts that are running are in the document root of
the virtual host being used – a reasonable idea. The complication is this: once
you untar the Baikal installation, you get a directory listing like this:

```
ChangeLog.md
Core/
INSTALL.md
LICENSE.txt
README.md
Specific/
TROUBLESHOOTING.md
UPGRADE.md
html/
vendor/
```

The document root must be set to the `html` directory above. So let’s say I
have a virtual host on `my.domain.tld` pointing to `/var/www/baikal/html`. This
doesn’t work because some of the scripts used in Baikal are in
`/var/www/baikal/Core/...` – *i.e.* not under `/var/www/baikal/html` and
therefore can’t be executed.

As far as I can see at the moment there are two “solutions” to the problem
(ignoring disabling suPHP):

  1.  Change the suPHP option to `check_vhost_docroot=false`.
  2.  Point the virtual host document root to `/var/www/baikal` instead and then
      access via `my.domain.tld/html`.

I like neither of these options, so until I find a real solution (which I will
post here if found), it seems that OwnCloud will be the way forwards.
Unfortunately, this does not sit well with me either. It is much more of a
sledgehammer approach when I’d prefer Baikal as a far more elegant solution.
Until I find a better way however...

[baikal]: http://baikal-server.com/
