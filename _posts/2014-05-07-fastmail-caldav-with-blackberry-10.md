---
title: "FastMail CalDAV with Blackberry 10"
date: 2014-05-07 16:40:44 +01:00
updated: 2014-09-21
categories: mobile
tags: blackberry fastmail
---
I have used FastMail for my email on and off for quite a long time; "on"
because it's brilliant – fast, works with everything (more or less) and looks
good and "off" because I like trying out everything (Gmail, Google Apps,
Outlook.com and Zoho to name a few).

Additionally, I have relatively recently become the owner of a Blackberry Q5
because:

  1.  I broke my Motorola Razr I,
  2.  I missed having *real* buttons,
  3.  I've never had a Blackberry before.

Since this isn’t a review of the Q5, I’ll keep it short – it’s really good, I
like BB10, and oh do I like the physical keyboard. I’m a long time Android
user, starting with the HTC Dream (T-Mobile G1) with a physical keyboard and
being just as spoilt with the HTC Desire Z. Whoa, I got sidetracked…

To the point of this post! FastMail have quite recently released their calendar
into an open beta, along with CalDAV support. I decided to get it syncing with
my phone because in BB10 this is a native capability (who’d have thought,
coming from Android...) I was disappointed to find that the autodiscovery URL
given by FastMail was met with a message saying that this account can’t be used
for whatever reason (I’ve forgotten the actual message).

I then thought, okay, so I just need to use the full URLs for each calendar and
will just have to set it up as three accounts – a little annoying but only
needs doing once. So I got my first “default” calendar syncing and decided that
I would do the others later. Pleasingly, having the default calendar syncing
syncs all of the calendars, so it seems that autodiscovery does work, but just
not with the autodiscover URL. This was particularly pleasing since the full
URLs for the non-default calendars are much longer, i.e. not this:

```
https://calendar.messagingengine.com/dav/calendars/user/USERNAME/CalendarName
```

But this:

```
https://calendar.messagingengine.com/dav/calendars/user/USERNAME/big-random-stream-of-numbers-and-letters-which-would-be-a-pain-to-type-even-on-a-blackberry
```

This is probably something that most people will end up working out for
themselves, but just in case...

### Update 21 September 2014
I have just done this again on a newer version of BBOS (10.2.1.2977) on my Q5
and it appears that the calendar name can be ignored, i.e. for Server Address
just use the following in order to sync all calendars:
`https://caldav.messagingengine.com/dav/calendars/user/USERNAME/`
