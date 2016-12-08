+++
title = "Pesky permalinks"
date = "2014-04-17T15:42:40+01:00"
categories = [ "linux" ]
tags = [ "apache", "wordpress" ]
+++
After multiple minor niggles when setting up the server and WordPress, the
thing that perplexed me most was getting the "pretty permalinks" to work, you
know `domain.tld/year/month/post-title-rather-than-id/` instead of
`domain.tld/?p=1984`. The document root for the website was writable by the
executing user and the `.htaccess` file got created, yet after the permalink
setup confirmation page, I received 403 forbidden errors from my web server
when trying to access any pages except the front page.

It turns out, although my web user had the permissions needed to do everything
necessary to the files, permalinks will not work until all the files under the
document root (or some of them...) are marked executable. Looking to the
[WordPress documentation][], all folders in the WordPress installation should
be `755` and all files, `644`. A couple of `chmod`s later and all was well!

```bash
chmod 755 -R /document/root
find /document/root -type d -exec chmod 755 {} \;
find /document/root -type f -exec chmod 644 {} \;
```

Although I initially found a post stating that all files and folders should
have `755` permissions except `./wp-admin/index.php` and `./.htaccess` which
should be `644`. Both sets work, but the former are more restrictive, so they
are the permissions that stuck.

[wordpress documentation]: http://codex.wordpress.org/Hardening_WordPress#File_Permissions
