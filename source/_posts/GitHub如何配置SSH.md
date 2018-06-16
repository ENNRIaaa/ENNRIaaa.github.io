title: GitHub如何配置SSH
date: 2018-06-12 16:16:26
description: GitHub配置SSH，今天学会的
categories: 生活随笔
tags: [hexo,GitHub]
toc: true
feature:

---
# 生成SSH Key #
在Git Bash终端输入命令：
<pre><code>
ssh-keygen -t rsa -C "china_liyan123@yahoo.co.jp"
</code></pre>
此处邮箱替换为自己的邮箱地址。  
此处终端提示：
>Generating public/private rsa key pair.  
>Enter file in which to save the key (/c/Users/shado/.ssh/id_rsa):  
<!--more-->  

终端会让你选择存放SSH的路径，括号内的是默认路径。
回车选择默认路径之后，终端提示输入SSH密码，输入两次，此时输入的密码不会显示在终端上，输入完直接回车就可以。  
>Your identification has been saved in /c/Users/shado/.ssh/id_rsa.  
>Your public key has been saved in /c/Users/shado/.ssh/id_rsa.pub.

之后终端提示密钥已经生成，在刚才选择的路径中，其中`id_rsa`是私有密钥，`id_rsa.pub`是公共密钥。  

# 在GitHub中添加密钥 #
登陆GitHub，在页面右上角头像下拉菜单中单机`Setting`，设置页面左侧有`SSH and GPG keys`,在这个标签页下添加SSH。  
右上角`New SSH key`，在本地刚刚保存SSH的路径，用文本编辑器打开`id_rsa.pub`，复制里面的内容，粘贴到`New SSH key`的key里面，Title自己定义一个标题就可以，之后Add。  
回到终端，输入命令：
<pre><code>
ssh -T git@github.com
</code></pre>
此时终端提示：  
>Enter passphrase for key '/c/Users/shado/.ssh/id_rsa':  

输入之前的密码，此时密码也是不会显示在终端上的。  
密码输入正确后，终端提示：  
>Hi ENNRIaaa! You've successfully authenticated, but GitHub does not provide shell access.

说明SSH密钥已经配置成功。
