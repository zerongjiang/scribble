---
layout: post
status: publish
published: true
title: boot beini from grub
author: admin
author_login: admin
author_email: denzeljiang@gmail.com
date: 2013-08-23 01:24:29
categories:
- Uncategorized
tags: []
comments: []
---

### [Beini](http://beini.es/) is [aircrack](http://en.wikipedia.org/wiki/Aircrack) tool box based on [TCL](http://en.wikipedia.org/wiki/Tiny_Core_Linux)

1.  unarchive beini iso file
2.  kernel file is bzImage

    pass `tce` parameter to kernel to load tce extensions

3.  initrd file is tinycore.gz

**Grub entry for beini**


```bash
root (hdx,y)
kernel /beini/boot/bzImage tinycore tce=sda1/beini/tce
initrd /beini/boot/tinycore.gz
```
