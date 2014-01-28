---
layout: post
status: publish
published: true
title: youtube-dl video formats
author: admin
author_login: admin
author_email: denzeljiang@gmail.com
wordpress_id: 478
wordpress_url: http://note.jzr.me/?p=478
date: 2013-07-20 02:21:58.000000000 -04:00
categories:
- Uncategorized
tags: []
comments: []
---

### [youtube-dl](http://rg3.github.io/youtube-dl/) is a python script to download videos from YouTube.com

**list all formats**

```bash
$ ./youtube-dl --get-format --all-formats {youtubeurl}
{num} quality
37 - 1080x1920
22 - 720x1280
35 - 480x854
34 - 360x640
18 - 360x640
5  - 240x400
17 - 144x176
```

**The num is explained here:**

http://en.wikipedia.org/wiki/YouTube#Quality_and_codecs

**download video of specified qulity**

`./youtube-dl -f {num} {youtubeurl}`
