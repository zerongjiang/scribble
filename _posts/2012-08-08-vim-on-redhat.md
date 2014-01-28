---
layout: post
status: publish
published: true
title: vim on redhat
author: admin
author_login: admin
author_email: denzeljiang@gmail.com
wordpress_id: 234
wordpress_url: http://note.jzr.me/?p=234
date: 2012-08-08 02:46:49.000000000 -04:00
categories:
- Uncategorized
tags: []
comments: []
---

```bash
./configure --prefix=/usr/local --enable-multibyte --with-features=huge --disable-selinux

make &amp; make install

alias vim='/usr/local/bin/vim'
```


make uninstall

