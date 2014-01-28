---
layout: post
status: publish
published: true
title: Install virtualbox on Archlinux
author: admin
author_login: admin
author_email: denzeljiang@gmail.com
date: 2011-09-03 07:14:25
categories:
- Uncategorized
tags:
- virtualbox
comments: []
---

virtualbox-ext-oracle 启用usb2.0支持

```bash
pacman -S virtualbox virtualbox-additions virtualbox-ext-oracle 

```

运行 VirtualBox

现在，将需要运行Virtualbox的用户名添加到vboxusers用户组：

```bash
gpasswd -a USERNAME vboxusers
```

创建必要的模块：

```bash
rc.d setup vboxdrv
```

最后，为了在启动时载入VirtualBox驱动，需要编辑{{Filename!/etc/rc.conf}}并添加vboxdrv到MODULES序列中：

```
ODULES=(... vboxdrv)
```

手动载入模块：

```bash
modprobe vboxdrv
```

共享文件：

```
net use x:\\vboxsrv\share
```