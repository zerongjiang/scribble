---
layout: post
status: publish
published: true
title: Enable sybase sql log
author: admin
author_login: admin
author_email: denzeljiang@gmail.com
wordpress_id: 515
wordpress_url: http://note.jzr.me/?p=515
date: 2013-10-21 18:44:37.000000000 -04:00
categories:
- Uncategorized
tags: []
comments: []
---

#### Enable sybase sql log

```sql
call sa_server_option('request_level_logging','SQL');
call sa_server_option('request_level_log_file',
                      'c:\sybaselog.txt');
```
---

#### Disable sybase sql log

```sql
call sa_server_option('request_level_log_file','');
```

---

#### Check log level and where is log file

```sql
select property('RequestLogFile'), property('RequestLogging');
```

##### Reference:
http://infocenter.sybase.com/help/index.jsp?topic=/com.sybase.infocenter.dc00170.1510/html/iqapgv1/BABIAEJJ.htm
