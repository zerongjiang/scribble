---
layout: post
status: publish
published: true
title: UTC for all systems
author: admin
author_login: admin
author_email: denzeljiang@gmail.com
date: 2011-09-03 07:22:10
categories:
- Uncategorized
tags: []
comments: []
---
Win:

```
Reg add HKLM\SYSTEM\CurrentControlSet\Control\TimeZoneInformation /v RealTimeIsUniversal /t REG_DWORD /d 1
```

ubuntu:
```
vim /etc/default/rcS
```
```
UTC=yes
```


time sync in archlinux

```
#ntpd -q
#ntpdate 0.us.pool.ntp.org 
#hwclock -w
```

check time

```
#timedatectl status
```
