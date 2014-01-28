---
layout: post
status: publish
published: true
title: improve sshfs performance
author: admin
author_login: admin
author_email: denzeljiang@gmail.com
wordpress_id: 416
wordpress_url: http://note.jzr.me/?p=416
date: 2013-05-06 19:55:26.000000000 -04:00
categories:
- Uncategorized
tags: []
comments: []
---

```bash
alias sshfs='sshfs -o Ciphers=arcfour -o cache_stat_timeout=600 -o workaround=nodelaysrv'
```

### Explain:

1. `Ciphers=arcfour` provides faster encryption method
2. default `cache_timeout` for {stat,dir,link} are all 20s. change `cache_stat_timeout` to 600s.
3. `nodelaysrv` - seems like improving network.

Add rename to workaround if you wanna have SVN work with sshfs.

### Todo:

1. Id Map: idmap={none,user,file}
2. fstab, on-demand mounting for sshfs

