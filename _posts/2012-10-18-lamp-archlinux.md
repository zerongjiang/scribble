---
layout: post
status: publish
published: true
title: LAMP archlinux
author: admin
author_login: admin
author_email: denzeljiang@gmail.com
date: 2012-10-18 19:30:11
categories:
- Uncategorized
tags: []
comments: []
---
---------------------------------------------------------------
#pacman -S apache php php-apache mysql

# grep http /etc/passwd
# useradd -d /srv/http -r -s /bin/false -U http

# vim /etc/hosts
127.0.0.1       localhost.localdomain   localhost yourhostname
::1             localhost.localdomain   localhost yourhostname

DAEMONS=(... httpd ...)

rc.d start httpd

--------------------------------------------------------------

Include conf/extra/httpd-userdir.conf

$ chmod o+x ~
$ chmod o+x ~/public_html
$ ln -s public_html www

-----------------------php----------------------------------
#vim /etc/httpd/conf/httpd.conf

LoadModule php5_module modules/libphp5.so

Include conf/extra/php5_module.conf

TypesConfig conf/mime.types

IMEMagicFile conf/magic

#vim /etc/httpd/conf/mime.types
application/x-httpd-php5		php php5

# rc.d restart httpd
<?php phpinfo(); ?>


----------------------mysql----------------------------------
# mysqladmin -u root password password
# mysql -u root -p

