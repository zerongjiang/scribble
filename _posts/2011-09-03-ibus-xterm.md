---
layout: post
status: publish
published: true
title: ibus xterm 中文输入
author: admin
author_login: admin
author_email: denzeljiang@gmail.com
date: 2011-09-03 07:21:38
categories:
- Uncategorized
tags: []
comments: []
---
1.确认export了以下输入法env：
```bash
export XMODIFIERS=@im=ibus
export GTK_IM_MODULE=ibus
export QT_IM_MODULE=ibus
```

2.指定xTerm的输入法
```bash
vim ~/.Xresources

!add this line
XTerm*inputMethod: ibus

#update
xrdb ~/.Xresources
```

3.ibus启动时必须加入--xim
```bash
ibus-daemon -xrd
```
