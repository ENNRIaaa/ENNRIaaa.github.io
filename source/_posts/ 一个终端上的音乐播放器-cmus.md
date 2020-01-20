title: 一个终端上的音乐播放器-cmus
date: 2018-06-16 23:06:26
description: 终端上的一个音乐播放器,回归原始?
categories: 生活随笔
tags: [cmus]
toc: true
feature:

---
# 前言 #
&ensp;&ensp;&ensp;&ensp;昨晚23点到今早3点多,看了两场世界杯.摩洛哥vs伊朗,葡萄牙vs西班牙.这是有生以来看的几场球赛.其实我对足球是一点儿也不懂的,裁判为什么判犯规,为什么黄牌,我也不知道.只是听解说,感觉很激情.看直播的心情很澎湃.今早伊朗以1:0的成绩取得胜利,比赛结束的一瞬间,赛场上有欢呼,有眼泪,有兴奋,有失落.每个人的心情都不同.那一瞬间,我感觉眼泪快掉下来了,赛场上的输和赢真是瞬息万变啊.生活亦如此.  
&ensp;&ensp;&ensp;&ensp;看完球赛,我重装了电脑系统.从deepin改到了mint linux.我本来是想要支持一下国产的linux的,但是我这一周的使用过程中发现,它真的很不稳定,bug特别的多.这感觉和我用linux的初衷相悖.linux给我的感觉应该是高效的,稳定的,安全的.而deepin正好相反.
&ensp;&ensp;&ensp;&ensp;今天在B站看视频,一个up主在讲linux,他用到了一个音乐播放器,终端上的,名叫`cmus`.这款播放器不是像我们在Windows上用的那样,带有图形界面的.我想,既然用了linux,就应该尽量脱离鼠标,没有什么是命令解决不了的.  
<!--more-->
# cmus安装 #
在终端输入命令,安装cmus:
<pre><code>
$ sudo apt-get install cmus
</code></pre>
我用的是mint linux,它是基于Ubuntu和Debian的,其他发行版的linux应该通过其他命令.安装完成之后输入命令,打开cmus:
<pre><code>
$ cmus
</code></pre>

# cmus使用 #
&ensp;&ensp;&ensp;&ensp;通过选择数字键盘1-7来切换各种界面模式,具体我是从1按到7,挨个试的.  
&ensp;&ensp;&ensp;&ensp;导入音乐路径,直接像vim编辑器一样,输入`:a /path/to/your/music/folder`  
&ensp;&ensp;&ensp;&ensp;下面是几个常用的按键:

>x 播放或重播音乐  
>c 暂停  
>b 播放下一首音乐  
>z 播放前一首音乐  
>s 激活随机播放

cmus用着感觉还不错,它虽然不像带有图形界面的播放器那样直观,但在使用过程中更让人有一种享受音乐的感觉.
