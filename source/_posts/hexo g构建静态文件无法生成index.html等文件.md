title: hexo g构建静态文件无法生成index.html等文件
date: 2018-06-16 04:12:26
description: 电脑重装系统,之后安装HEXO出现的问题
categories: 生活随笔
tags: [hexo]
toc: true
feature:

---
# 问题现象 #
安装好`nodejs`,`git`,`HEXO`之后,在GitHub上重新克隆hexo源文件到本地,然后通过`hexo c`,`hexo g`命令后,`public`文件夹内没有`index.html`等文件.  
<!--more-->
# 检查npm插件 #
<pre><code>
npm ls --depth 0
</code></pre>
通过命令查看缺少的插件,终端会提示很多`npm ERR!`

# 解决方法 #
<pre><code>
npm install hexo-generator-archive --save
</code></pre>
安装后重新`hexo c`,`hexo g`即可.

# 题外话 #
我今天通过上述方法解决了没有`index.html`的问题,但是生成的`index.html`是空的.后来我发现是`themes`里面的主题,只有个主题文件夹,把主题的文件夹打开之后,发现里面为空.之后重新下主题文件放进去就好了.
