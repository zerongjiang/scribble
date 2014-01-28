---
layout: post
status: publish
published: true
title: VMWare 7.1.4 on archlinux kernel 3.0
author: admin
author_login: admin
author_email: denzeljiang@gmail.com
date: 2011-09-05 07:21:51
categories:
- Uncategorized
tags: []
comments: []
---
试了一下archlinux下的vmware，kernel太新了，虽然看着wiki安装，跑了起来，但是感觉很慢。

不知道什么问题，懒得去折腾了。

不过安装的时候看到这个倒是挺有用的，虽然对大部分目录的用途都有概念，不过看到/usr/sbin和/usr/bin的区别时还是大吃一惊，原来sbin时这个意思。。。


System path prefix.  Please note that choosing a path other than /usr
may result in missing icons, application launchers, and other desktop
integrations [/usr]: 

System lib directory [/usr/lib]: 

Architecture-independent files [/usr/share]: 

User level binaries [/usr/bin]: 

Super user level binaries [/usr/sbin]: 

Documentation [/usr/share/doc]: 

manual pages [/usr/share/man]: 

Header files [/usr/include]: 

System configuration files [/etc]: 

System service runlevel directory (contains rc?.d directories).  Use
an empty directory if your system does not support rc?.d style
directories: /etc/rc.d/vmware.d/

System service scripts directory (commonly /etc/init.d)
[/etc/rc.d/vmware.d/init.d]: /etc/rc.d

---附安装过程--

创建arch下vmware的配置目录：
```bash
# mkdir -p /etc/rc.d/vmware.d/{rc{0..6},init}.d
# chmod +x VMware-<edition>-<version>.<release>.<architecture>.bundle
# ./VMware-<edition>-<version>.<release>.<architecture>.bundle --console --custom
```

修改这两个安装选项：

Set System service runlevel
/etc/rc.d/vmware.d/

Set System service scripts to:
/etc/rc.d

安装完成后，patch kernel 3.x 和 kernel 2.6.xx 不兼容的问题。具体来讲就是uname -a，新版本kernel输出格式和以前不同了。
这个是archlinux论坛geek直接修改二进制so的方法。非常牛逼。
<pre class="brush:shell">
# sed 's/\x83\xe8\x03\x83\xf8\x01\x0f\x96\xc0/\x83\xe8\x02\x83\xf8\x01\x0f\x96\xc0/' -i /usr/lib/vmware/lib/libvmware-modconfig-console.so/libvmware-modconfig-console.so
# sed 's/\x83\xe8\x03\x83\xf8\x01\x0f\x96\xc0/\x83\xe8\x02\x83\xf8\x01\x0f\x96\xc0/' -i /usr/lib/vmware/lib/libvmware-modconfig.so/libvmware-modconfig.so</pre>

修改vmware脚本中lsmod位置。
<pre class="brush:shell">
#sed -i "s|/sbin/lsmod|/bin/lsmod|g" /etc/rc.d/vmware</pre>

去这里下载patch:
http://weltall.heliohost.org/wordpress/2011/05/14/running-vmware-workstation-player-on-linux-2-6-39-updated/
虽然这个是2.6.39的，貌似3.0也可以用。运行patch看到所有module编译完成并启用就可以运行vmware了。

good luck。
