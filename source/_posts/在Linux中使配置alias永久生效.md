title: 在Linux中使配置alias永久生效
date: 2018-06-13 15:06:45
description: alias简化了命令，但是每一次都要重新配置有很困扰
categories: 生活随笔
tags: [Linux,alias]
toc: true
feature:

---
# 编辑.bashrc #
在终端，通过命令回家：
<pre><code>
cd ~
</code></pre>
之后通过文本编辑器编辑文本`.bashrc`：
<pre><code>
sudo gedit .bashrc
</code></pre>
或者，使用vim编辑：
<pre><code>
sudo vim .bashrc
</code></pre>
<!--more-->
如果没有`.bashrc`文件，可以自己创建一个，创建也使用上面的命令。  
*注：`.bashrc`是隐藏文件，在文件管理器中查看时需要勾选`显示隐藏文件`。*  
在`.bashrc`最后一行添加你要设置的alias命令，例如：
<pre><code>
alias hxc='rm -f ~/blog/db.json && hexo clean'
</code></pre>  
如果是新建的`.bashrc`文件，直接在里面添加alias命令就可以，命令是一行一行的。  
添加完之后保存，再通过source命令使刚才的配置文件生效：  
<pre><code>
source .bashrc
</code></pre>
再在终端敲击`alias`命令，查看已经配置的alias命令，发现刚才编辑的命令都已经出现了。
# 编辑.bash_profile #
在`.bash_profile`最后一行添加一条命令：
<pre><code>  
source ~/.bash_profile
</code></pre>
注：如果没有`.bash_profile`文件就新建一个。  
添加完之后保存退出，终端通过source命令使配置生效：
<pre><code>
source .bash_profile
</code></pre>
此时可以重新打开终端，输入`alias`命令，查看配置的alias是否已经生效。
