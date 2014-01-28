---
layout: post
status: publish
published: true
title: solarized color scheme for chrome nassh secure shell
author: admin
author_login: admin
author_email: denzeljiang@gmail.com
wordpress_id: 494
wordpress_url: http://note.jzr.me/?p=494
date: 2013-09-07 21:48:23.000000000 -04:00
categories:
- Uncategorized
tags: []
comments: []
---

```js
[solarized-dark]
    color-palette-override:{"0":"#073642","1":"#dc322f","2":"#859900","3":"#b58900","4":"#268bd2","5":"#d33682","6":"#2aa198","7":"#eee8d5","8":"#002b36","9":"#cb4b16","10":"#586e75","11":"#657b83","12":"#839496","13":"#6c71c4","14":"#93a1a1","15":"#fdf6e3"}
    background-color : "#002b36"
    cursor-color     : "#eee8d5"
    foreground-color : "#eee8d5"

[solarized-light]
    color-palette-override:{"0":"#073642","1":"#dc322f","2":"#859900","3":"#b58900","4":"#268bd2","5":"#d33682","6":"#2aa198","7":"#eee8d5","8":"#002b36","9":"#cb4b16","10":"#586e75","11":"#657b83","12":"#839496","13":"#6c71c4","14":"#93a1a1","15":"#fdf6e3"}
    background_color : "#eee8d5"
    cursor_color     : "#002b36"
    foreground_color : "#002b36"
```

### Howto:

1. open a new tab in chrome and switch to app page
2. right-click on the secure shell icon
3. left-click options
4. enter the values needed. check config file for details
5. open a new connection in secure shell, choose the profile u just edited/created

Ref:

https://github.com/yuex/chrome-secure-shell-solarized
