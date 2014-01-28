---
layout: post
status: publish
published: true
title: github add new ssh keys
author: admin
author_login: admin
author_email: denzeljiang@gmail.com
wordpress_id: 209
wordpress_url: http://note.jzr.me/?p=209
date: 2012-06-16 05:12:44.000000000 -04:00
categories:
- Uncategorized
tags: []
comments: []
---
cd ~/.ssh

#ssh-keygen -t rsa -C JZR-Ubuntu

-C some comment

cat id_rsa.pub -n > sshkey
