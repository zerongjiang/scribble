---
layout: post
status: publish
published: true
title: thinkpad trackpoint&synaptics配置
author: admin
author_login: admin
author_email: denzeljiang@gmail.com
date: 2011-09-03 07:16:07
categories:
- Uncategorized
tags:
- thinkpad
comments: []
---
1.trackpoint中键滚轮
ubuntu: vim /usr/share/X11/xorg.conf.d/20-thinkpad.conf
arch: vim /etc/X11/xorg.conf.d/20-thinkpad.conf

```
Section "InputClass"
	Identifier	"Trackpoint Wheel Emulation"
	MatchProduct	"TPPS/2 IBM TrackPoint|DualPoint Stick|Synaptics Inc. Composite TouchPad / TrackPoint|ThinkPad USB Keyboard with TrackPoint|USB Trackpoint pointing device|Composite TouchPad / TrackPoint"
	MatchDevicePath	"/dev/input/event*"
	Option		"EmulateWheel"		"true"
	Option		"EmulateWheelButton"	"2"
	Option		"Emulate3Buttons"	"false"
	Option		"XAxisMapping"		"6 7"
	Option		"YAxisMapping"		"4 5"
EndSection
```

2.trackpoint灵敏度和速度

vim /etc/rc.local

```bash
sleep 5
echo -n 120 > /sys/devices/platform/i8042/serio1/serio2/speed
echo -n 250 > /sys/devices/platform/i8042/serio1/serio2/sensitivity
```

3.synaptics配置
vim /etc/X11/xorg.conf.d/10-synaptics.conf

```
Section "InputClass"
        Identifier "touchpad catchall"
        Driver "synaptics"
        MatchIsTouchpad "on"
        MatchDevicePath "/dev/input/event*"
                #tap
                Option "TapButton1" "1"
                Option "TapButton2" "3"
                Option "TapButton3" "3"

                #scrolling
                Option "CircularScrolling" "on"
                Option "CircScrollTrigger" "1"

                Option "VertEdgeScroll" "on"
EndSection
```

在/etc/udev/rules.d/下新建一个文件：10-trackpoint.rules
里面写入如下信息：

```
SUBSYSTEM=="serio", DRIVERS=="psmouse", WAIT_FOR="/sys/devices/platform/i8042/serio1/serio2/sensitivity", ATTR{sensitivity}="250"
SUBSYSTEM=="serio", DRIVERS=="psmouse", WAIT_FOR="/sys/devices/platform/i8042/serio1/serio2/speed", ATTR{speed}="150"
```

注意WAIT_FOR后面的路径换成你的有效路径，就是serio4/serio5之类的，保存退出，下次重启之后就行了
