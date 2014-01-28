---
layout: post
status: publish
published: true
title: Merge flv videos by ffmpeg
author: admin
author_login: admin
author_email: denzeljiang@gmail.com
date: 2013-07-01 15:42:15
categories:
- Uncategorized
tags: []
comments: []
---

### Suppose you need to merge 1..5.flv into one video

```bash
$ tree
videos
├── 1.flv
├── 2.flv
├── 3.flv
├── 4.flv
└── 5.flv
```

**This command do the trick:**

```bash
$ for f in *.flv; do echo "file '$(pwd)/$f'" >> list ; done
$ ffmpeg -f concat -i list -c copy merged.flv
```
