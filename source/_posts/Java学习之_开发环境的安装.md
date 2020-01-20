title: Java学习之_开发环境的安装
date: 2018-04-13 21:51
toc: true

---

在学习Java开发之前，需要做一些准备工作，   
Java开发需要安装JDK（Java开发工具集），JDK里面包括Java编译器，和JRE（Java运行时环境），其中JRE里面又包含JVM（Java虚拟机）、Java核心类库以及一些支持文件。   
所以，想要学习Java，必须得先安装JDK。（只为了运行Java程序，只需安装JRE就可以了）  

---
我们可以到甲骨文官方的JDK下载地址：http://www.oracle.com/technetwork/java/javase/downloads/index.html   
下载好后直接安装就可以了。   
![请输入图片描述][1]


安装完成之后还有一步，就是需要给系统配置Java环境变量。  

![请输入图片描述][2]


配置环境变量是在：桌面计算机右键属性-->高级系统设置-->环境变量  
编辑Path，最简单的方法就是到Java的安装路径  
![请输入图片描述][3]


把这个路径直接复制粘贴到Path中，如果是win10之前的版本，每个路径之间用“;”隔开，注意：分号是英文输入状态下的
![请输入图片描述][4]


这时，ctrl+R，cmd命令： 



![请输入图片描述][5]


在cmd里敲javac和java试试，这时说明java环境变量已经配置成功了。 
如果没有配置成功，会显示其不是内部或外部命令，也不是可运行的程序或批处理文件。  

---
以上是Java的安装及配置部分。 
接下来是开发工具的安装，Java常用的开发工具有eclipse、myeclipse，IDEA等，后两个是需要付费的，我们只需要安装eclipse就可以。 
eclipse可以直接百度eclipse官网就可以下载安装了，安装过程都是十分简单，我就不介绍了。 
![请输入图片描述][6]我安装的是myeclipse，界面大致就是这样的： 


这是我写的一个双色球的代码：利用的随机数和集合，我也是刚刚学到这里 
![请输入图片描述][7]


运行结果： 
![请输入图片描述][8]


  [1]: https://images.shiguangping.com/images/Java%E5%AD%A6%E4%B9%A0%E4%B9%8B_%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83%E5%AE%89%E8%A3%85/Java%E5%AD%A6%E4%B9%A0%E4%B9%8B_%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83%E5%AE%89%E8%A3%85_%E5%9B%BE1.png
  [2]: https://images.shiguangping.com/images/Java%E5%AD%A6%E4%B9%A0%E4%B9%8B_%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83%E5%AE%89%E8%A3%85/Java%E5%AD%A6%E4%B9%A0%E4%B9%8B_%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83%E5%AE%89%E8%A3%85_%E5%9B%BE2.png
  [3]: https://images.shiguangping.com/images/Java%E5%AD%A6%E4%B9%A0%E4%B9%8B_%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83%E5%AE%89%E8%A3%85/Java%E5%AD%A6%E4%B9%A0%E4%B9%8B_%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83%E5%AE%89%E8%A3%85_%E5%9B%BE3.png
  [4]: https://images.shiguangping.com/images/Java%E5%AD%A6%E4%B9%A0%E4%B9%8B_%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83%E5%AE%89%E8%A3%85/Java%E5%AD%A6%E4%B9%A0%E4%B9%8B_%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83%E5%AE%89%E8%A3%85_%E5%9B%BE4.png
  [5]: https://images.shiguangping.com/images/Java%E5%AD%A6%E4%B9%A0%E4%B9%8B_%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83%E5%AE%89%E8%A3%85/Java%E5%AD%A6%E4%B9%A0%E4%B9%8B_%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83%E5%AE%89%E8%A3%85_%E5%9B%BE5.png
  [6]: https://images.shiguangping.com/images/Java%E5%AD%A6%E4%B9%A0%E4%B9%8B_%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83%E5%AE%89%E8%A3%85/Java%E5%AD%A6%E4%B9%A0%E4%B9%8B_%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83%E5%AE%89%E8%A3%85_%E5%9B%BE6.png
  [7]: https://images.shiguangping.com/images/Java%E5%AD%A6%E4%B9%A0%E4%B9%8B_%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83%E5%AE%89%E8%A3%85/Java%E5%AD%A6%E4%B9%A0%E4%B9%8B_%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83%E5%AE%89%E8%A3%85_%E5%9B%BE7.png
  [8]: https://images.shiguangping.com/images/Java%E5%AD%A6%E4%B9%A0%E4%B9%8B_%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83%E5%AE%89%E8%A3%85/Java%E5%AD%A6%E4%B9%A0%E4%B9%8B_%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83%E5%AE%89%E8%A3%85_%E5%9B%BE8.png

---
这个程序运行第一次的结果，我照着买了一注相同的号码，可惜就中了前两个号码
以上就介绍到这了~拜拜