---
layout: post
status: publish
published: true
title: best way to configure trackpoint
author: admin
author_login: admin
author_email: denzeljiang@gmail.com
date: 2012-09-11 20:47:45
categories:
- Uncategorized
tags: []
comments: []
---
/etc/udev/rules.d/trackpoint.rules

```
SUBSYSTEM=="serio", DRIVERS=="psmouse", WAIT_FOR="/sys/devices/platform/i8042/serio1/serio2/sensitivity", ATTR{sensitivity}="200", ATTR{speed}="150"
```