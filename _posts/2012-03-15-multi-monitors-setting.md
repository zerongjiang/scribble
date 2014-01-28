---
layout: post
status: publish
published: true
title: multi-monitors setting
author: admin
author_login: admin
author_email: denzeljiang@gmail.com
wordpress_id: 120
wordpress_url: http://note.jzr.me/?p=120
date: 2012-03-15 06:21:53.000000000 -04:00
categories:
- Uncategorized
tags: []
comments: []
---
```bash
xrandr --output LVDS1 --auto --primary --output VGA1 --auto --right-of LVDS1
```

Add this to rc.lua to enable key bindlings
thinkpad的显示屏切换组合键可以用来绑定设置

```lua
    --MultiScreen
    awful.key({ }, "XF86Display"        ,
                function ()
                        awful.util.spawn("xrandr --output LVDS1 --auto --primary --output VGA1 --auto --right-of LVDS1")
                end),
```

xev:  get x11 key value
xpro: get x windows properties 
