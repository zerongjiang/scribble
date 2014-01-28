---
layout: post
status: publish
published: true
title: 'awesome thinkpad volume hotkey '
author: admin
author_login: admin
author_email: denzeljiang@gmail.com
date: 2011-09-03 07:19:09
categories:
- Uncategorized
tags: []
comments: []
---
awesome下ThinkPad的音量控制
vim ~/.config/awesome/rc.lua

```lua
globalkeys = awful.util.table.join(
...,
awful.key({ }, "XF86AudioRaiseVolume", function () awful.util.spawn_with_shell("amixer set Master 2%+") end),
awful.key({ }, "XF86AudioLowerVolume", function () awful.util.spawn_with_shell("amixer set Master 2%-") end),
awful.key({ }, "XF86AudioMute", function () awful.util.spawn_with_shell("amixer set Master toggle") end),
....
)
```
