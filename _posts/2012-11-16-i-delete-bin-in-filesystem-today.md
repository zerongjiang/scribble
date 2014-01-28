---
layout: post
status: publish
published: true
title: 今天把bin给删了。。。
author: admin
author_login: admin
author_email: denzeljiang@gmail.com
date: 2012-11-16 00:56:27
categories:
- Uncategorized
tags: []
comments: []
---

去irc求助大神：

似乎满血复活了

pacman -Qk 搜索missing file的包，然后重新安装。

﻿﻿﻿﻿pacman -Qqk |awk '!a[$1]++ {print $1}' |grep -Fv -f <(pacman -Qqm) | pacman -S -
