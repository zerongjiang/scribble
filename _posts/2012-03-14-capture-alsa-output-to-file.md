---
layout: post
status: publish
published: true
title: capture alsa output to file
author: admin
author_login: admin
author_email: denzeljiang@gmail.com
wordpress_id: 145
wordpress_url: http://note.jzr.me/?p=145
date: 2012-03-14 07:02:49.000000000 -04:00
categories:
- Uncategorized
tags: []
comments: []
---
我的声卡没有硬件mixer，打开alsamixer，只有capture from mic，无法capture到speaker的声音。

Intel HDA的集成声卡貌似都不支持硬件mixer。

无奈用ffmpeg做屏幕录像和录音的时候就无法录到speaker的声音。

放狗搜到一个曲线救国的方法：
<pre class="brush:shell">vim ~/.asoundrc

pcm.!default {
  type empty
  slave {
    pcm "tee:'plughw:0,0','/tmp/alsa_capture.wav',wav"
  }
}</pre>
linux的一大特性是所有的device其实都是一个可以读写的文件流。

.asoundrc 是 alsa audio server的配置，可以保存音频到文件。

附ffmpeg screen casting 代码：
<pre class="brush:shell">ffmpeg -f alsa -ac 2 -i hw:0,0 -f x11grab -r 30 -s 1440x900 -i 0:0+0,0 -acodec ppcm_s16le -vcodec libx264 -preset ultrafast -threads 0 output.mkv</pre>
Ref:
<a href="http://blog.csdn.net/jixiuffff/article/details/5709976" target="_blank"> 关于ffmpeg 的总结</a>

<a href="http://www.swview.org/node/213" target="_blank"> How to redirect the ALSA output to a file</a>
