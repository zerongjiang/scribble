---
layout: post
status: publish
published: true
title: pure systemd
author: admin
author_login: admin
author_email: denzeljiang@gmail.com
date: 2012-11-08 22:59:54
categories:
- Uncategorized
tags: []
comments: []
---
<h3>Mixed systemd/sysvinit/initscripts</h3>
把/etc/rc,conf 的大部分配置迁移为新的native systemd configuration files,

只保留自动启动的daemon部分。

systemd会负责启动 daemon list。

启动时内核参数加入 init=/usr/lib/systemd/systemd

--

按照 Systemd 原生配置文件的介绍，将<code>/etc/rc.conf</code>中的段落替换为相应的配置文件：
<table>
<tbody>
<tr>
<th scope="col">配置内容</th>
<th scope="col">配置文件</th>
<th scope="col">老<code>/etc/rc.conf</code>段落</th>
</tr>
<tr>
<td>Hostname</td>
<td><code>/etc/hostname</code><code>/etc/hosts</code></td>
<td><code>NETWORKING</code></td>
</tr>
<tr>
<td>终端字体和键盘映射</td>
<td><code>/etc/vconsole.conf</code></td>
<td><code>LOCALIZATION</code></td>
</tr>
<tr>
<td>Locale</td>
<td><code>/etc/locale.conf</code><code>/etc/locale.gen</code></td>
<td><code>LOCALIZATION</code></td>
</tr>
<tr>
<td>时区</td>
<td><code>/etc/localtime</code><code>/etc/localtime</code></td>
<td><code>LOCALIZATION</code></td>
</tr>
<tr>
<td>硬件时钟</td>
<td><code>/etc/adjtime</code></td>
<td><code>LOCALIZATION</code></td>
</tr>
<tr>
<td>内核模块</td>
<td><code>/etc/modules-load.d/</code></td>
<td><code>HARDWARE</code></td>
</tr>
<tr>
<td>Daemons</td>
<td><code>/etc/rc.conf</code></td>
<td><code>DAEMONS</code></td>
</tr>
<tr>
<td>有线网络</td>
<td><code>/etc/rc.conf</code></td>
<td><code>NETWORKING</code></td>
</tr>
</tbody>
</table>
因为历史原因，<code>/etc/rc.conf</code>中的<strong>DAEMONS</strong>段落依然与 systemd 兼容。

---
<h3>Mixed systemd/initscripts installation</h3>
用 systemdctl enable daemonName 替换 rc,conf 中的daemon list

安装systemd-sysvcompat 代替 sysvinit， 这样不用内核参数就能从systemd启动了。

&nbsp;
<h3>Pure systemd installation</h3>
当你确定系统运星无误，rc.conf内没有任何你要启动的daemon，已经全部转移倒systemd下的时候，

就可以删除initscripts

/etc/rc.conf /etc/rc.local /etc/rc.local.shutdown 这三个文件也不在需要了。
<h3>Tips：</h3>
从systemd不在需要用户需要在 optical, audio, scanner, etc 组中。可以从这些组删除。
<pre># gpasswd -d [user] [group]</pre>
<pre>用户组的变化： https://wiki.archlinux.org/index.php/Users_and_Groups</pre>
关于 日志 和 cron job： systemd有自己的日志系统journal（用法见wiki），可以将syslog-ng 删除。

crond用&nbsp;cronie.service 代替。

dbus在启动某些服务后会被自动调用 。

查看可以启用的service：
<pre>systemctl list-units</pre>
<pre></pre>
<h4>有趣的东西：</h4>
<pre>启动分析图：</pre>
<pre>systemd-analyze plot > plot.svg</pre>
<pre>启动read ahead优化：</pre>
<pre>systemctl enable systemd-readahead-collect.service systemd-readahead-replay.service</pre>
<pre></pre>
<pre></pre>
<pre></pre>
<pre></pre>
&nbsp;
