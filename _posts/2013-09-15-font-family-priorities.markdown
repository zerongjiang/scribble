---
layout: post
status: publish
published: true
title: font-family priorities
author: admin
author_login: admin
author_email: denzeljiang@gmail.com
wordpress_id: 496
wordpress_url: http://note.jzr.me/?p=496
date: 2013-09-15 01:51:15.000000000 -04:00
categories:
- Uncategorized
tags: []
comments: []
---

## Rule:

1. English name first
2. Apple fist
3. Add fall back
4. add font alias
5. back compatible

```css
font-family: Helvetica, Tahoma, Arial, STXihei, "华文细黑", "Microsoft YaHei", "微软雅黑", SimSun, "宋体", Heiti, "黑体", sans-serif;
```
**Font fall back chain:**

Non-chinese: Helvetica -> Tahoma -> Arial

Chinese:     华文细黑 -> 微软雅黑 -> 宋体

---

### Check fonts in linux

refresh font

`fc-cache -vf`

list all font

`fc-list`

---

References:

css font-family guide for chinese: http://ruby-china.org/topics/14005
