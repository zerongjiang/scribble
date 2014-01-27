---
layout: post
status: publish
published: true
title: Jelly Bean usb tethering to archlinux
author: admin
author_login: admin
author_email: denzeljiang@gmail.com
wordpress_id: 239
wordpress_url: http://note.jzr.me/?p=239
date: 2012-08-20 17:35:19.000000000 -04:00
categories:
- Uncategorized
tags: []
comments: []
---

```bash
# modprobe usbnet
# ifconfig usb0 up && dhcpcd usb0
# ifconfig -a
```

Ref:https://wiki.archlinux.org/index.php/Android_Tethering