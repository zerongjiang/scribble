---
layout: post
status: publish
published: true
title: archlinux binaries merging
author: admin
author_login: admin
author_email: denzeljiang@gmail.com
date: 2013-06-12 17:50:36
categories:
- Uncategorized
tags: []
comments: []
---
1. find no-official pkg need to fix:

   `pacman -Qqo /bin /sbin /usr/sbin | pacman -Qm -`

2. update official pkgs

   `pacman -Syu --ignore filesystem,bash`

3. find&move binaries in deprecated folder

   `find /bin /sbin /usr/sbin`

   `move /bin/* /usr/bin`

   `move /sbin/* /usr/bin`

   `move /usr/sbin/* /usr/bin`

4. update bash, filesystem

   `pacman -S bash`

   `pacman -Su`

5. update no-official pkg

   `yaourt -Syu`

Tip:
open couple of bash during update for rescue.
