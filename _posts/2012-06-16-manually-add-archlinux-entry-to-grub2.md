---
layout: post
status: publish
published: true
title: 'manually add archlinux entry to grub2 '
author: admin
author_login: admin
author_email: denzeljiang@gmail.com
date: 2012-06-16 05:02:37
categories:
- Uncategorized
tags: []
comments: []
---
#vim /etc/grub.d/40_custom


```
menuentry "Arch Linux" {
    insmod part_msdos
    insmod jfs
    set root='(hd0,msdos7)'
    linux /boot/vmlinuz-linux root=/dev/sda7 ro
    initrd /boot/initramfs-linux.img
}
```

#update-grub
