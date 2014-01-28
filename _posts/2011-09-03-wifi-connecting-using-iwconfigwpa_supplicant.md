---
layout: post
status: publish
published: true
title: wifi connecting using iwconfig&wpa_supplicant
author: admin
author_login: admin
author_email: denzeljiang@gmail.com
date: 2011-09-03 07:19:30
categories:
- Uncategorized
tags: []
comments: []
---
make sure the driver works, and wlan0 could be see from ifconfig.

Show WiFi near you.

```bash
iwlist wlan0 scan
```

For WPA-Encryption WiFi

```bash
mv /etc/wpa_supplicant.conf /etc/wpa_supplicant.conf.original
wpa_passphrase linksys "my_secret_passkey" > /etc/wpa_supplicant.conf
```

Connecting ...

|Encryption	            |Command
|-----------------------|---------------------------------------------------------------
|No Encryption          | iwconfig wlan0 essid "linksys"
|WEP w/ Hex Key         | iwconfig wlan0 essid "linksys" key "0241baf34c"
|WEP w/ ASCII passphrase| iwconfig wlan0 essid "linksys" key "s:pass1"
|WPA	                | wpa_supplicant -B -Dwext -i wlan0 -c /etc/wpa_supplicant.conf

check WiFi status:

```bash
dhcpcd wlan0
iwconfig
```
