---
layout: post
status: publish
published: true
title: if android sdk couldn&rsquo;t find your JDK
author: admin
author_login: admin
author_email: denzeljiang@gmail.com
wordpress_id: 104
wordpress_url: http://note.jzr.me/uncategorized/if-android-sdk-couldnt-find-your-jdk/
date: 2011-09-13 05:05:07.000000000 -04:00
categories:
- Uncategorized
tags: []
comments: []
---
![](http://note.jzr.me/wp-content/uploads/2011/09/ScreenClip.png)

JAVA_HOME   = JDK_Path

Path        += .;%JAVA_HOME%\bin

CLASSPATH   += ;%JAVA_HOME%/lib/dt.jar;%JAVA_HOME%/lib/tools.jar