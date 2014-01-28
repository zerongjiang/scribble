---
layout: post
status: publish
published: true
title: windows bat to add hosts
author: admin
author_login: admin
author_email: denzeljiang@gmail.com
wordpress_id: 423
wordpress_url: http://note.jzr.me/?p=423
date: 2013-05-14 15:57:48.000000000 -04:00
categories:
- Uncategorized
tags: []
comments: []
---

### Point domain.com to 127.0.0.1

```bat
@echo off
set hostspath=%windir%\System32\drivers\etc\hosts
echo. >> %hostspath%
REM echo #comment>> %hostspath%
echo 127.0.0.1 www.domain.com>> %hostspath%
echo 127.0.0.1 domain.com>> %hostspath%
ipconfig /flushdns
exit
```


### Clean up

```bat
REM This bat remove all entries of domain.com from hosts file
findstr /v domain.com^
        C:\WINDOWS\system32\drivers\etc\hosts^
        > C:\WINDOWS\system32\drivers\etc\hosts.tmp

copy C:\WINDOWS\system32\drivers\etc\hosts.tmp^
     C:\WINDOWS\system32\drivers\etc\hosts

del C:\WINDOWS\system32\drivers\etc\hosts.tmp
```


### Some tips

```bat
REM make new line
echo.
echo:
```


##### References:

http://www.microsoft.com/resources/documentation/windows/xp/all/proddocs/en-us/findstr.mspx
