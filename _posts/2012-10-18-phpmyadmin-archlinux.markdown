---
layout: post
status: publish
published: true
title: phpmyadmin archlinux
author: admin
author_login: admin
author_email: denzeljiang@gmail.com
wordpress_id: 323
wordpress_url: http://note.jzr.me/?p=323
date: 2012-10-18 21:09:25.000000000 -04:00
categories:
- Uncategorized
tags: []
comments: []
---
#pacman -S phpmyadmin php-mcrypt

cp /etc/webapps/phpmyadmin/apache.example.conf /etc/httpd/conf/extra/httpd-phpmyadmin.conf

# vim /etc/httpd/conf/httpd.conf
Include conf/extra/httpd-phpmyadmin.conf

#vim /etc/webapps/phpmyadmin/.htaccess
#deny from all
allow from 127.0.0.1
allow from ::1

// uncomment
extension=mcrypt.so

