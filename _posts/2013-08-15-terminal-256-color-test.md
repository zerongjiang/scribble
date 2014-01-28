---
layout: post
status: publish
published: true
title: terminal 256 color test script
author: admin
author_login: admin
author_email: denzeljiang@gmail.com
date: 2013-08-15 15:42:32
categories:
- Uncategorized
tags: []
comments: []
---

### Display all 256 colors

Prints all 256 colors across the screen, very quick.

```bash
(x=`tput op` y=`printf %76s`;for i in {0..256};do o=00$i;echo -e ${o:${#o}-3:3} `tput setaf $i;tput setab $i`${y// /=}$x;done)
```
