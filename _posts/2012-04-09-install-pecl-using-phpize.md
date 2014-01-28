---
layout: post
status: publish
published: true
title: install pecl using phpize
author: admin
author_login: admin
author_email: denzeljiang@gmail.com
date: 2012-04-09 23:06:52
categories:
- Uncategorized
tags: []
comments: []
---
perl = PHP Extension Community Library

imagick是个功能强大的图像处理程序。功能，执行效率，支持的格式都比GD强很多。

php提供了三种api可以执行imagick：http://www.imagemagick.org/script/api.php

agickWand for php
IMagick
phMagick

这里选择比较流行的的IMagick： http://pecl.php.net/package/imagick

下载最新的stable，解压，安装：

<pre class="brush:shell">
$cd extname
$ phpize
$ ./configure
$ make
# make install</pre>
