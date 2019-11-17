title: Linux学习之~ubuntu安装jdk及配置环境变量
date: 2018-05-15 00:00
toc: true

---
安装方式有很多种，我写的只是其中之一。（网站由于一些原因无法复制文字，建议手动敲命令）

## 一，官网下载jdk ##

前往jdk官网下载jdk，地址：http://www.oracle.com/technetwork/java/javase/downloads/index.html

![请输入图片描述][1]


现在已经更新到jdk10了，但是我下载解压之后发现里面没有jre文件夹，不知为何，可能是我下载的不对，但是为了不发生同样的问题，推荐下载之前的版本。

（文章具有一定的时效性，不代表很久以后也是这样）

![请输入图片描述][2]


我下载的是linux x64的版本，jdk-8u172-linux-x64.tar.gz

ubuntu系统的话，默认会下载到“下载”里面（我用的ubuntu版本是18.04LTS）

## 二，创建文件夹，jdk解压到该文件夹内 ##
1，进到/usr/lib/文件夹下，


    cd /usr/lib

![请输入图片描述][3]


在当前文件夹输入sudo mkdir jvm创建文件夹

    sudo mkdir jvm

此时可以用命令查看文件夹是否创建成功

    ls -l

看看是否有jvm这个文件夹。
![请输入图片描述][4]


2，然后利用cd命令回到“下载”文件夹，把下载好的jdk移动到刚刚创建的jvm文件夹

    sudo mv jdk-8u172-linux-x64.tar.gz /usr/lib/jvm

然后进入/usr/lib/jvm文件夹，查看该文件是否存在

3，用tar -zxvf命令解压

    sudo tar -zxvf jdk-8u172-linux-x64.tar.gz

解压完成后可以用ls -l命令查看以下是否解压成功

（注：在2步骤时，可以在下载文件夹直接将下载好的jdk解压到目标目录/usr/lib/jvm里，然后在回到jvm目录查看是否解压成功）

解压到目标目录的命令是，这个记得不太清楚

    sudo tar -zxvf jdk-8u172-linux-x64.tar.gz -C /usr/lib/jvm

应该是这个命令。

## 三，配置环境变量 ##

解压成功后开始配置环境变量

sudo gedit ~/.bashrc
这时会出现一个文本框

![请输入图片描述][5]


在结尾fi后面加上这四段代码：

    export JAVA_HOME=/usr/lib/jvm/jdk1.8.0_171
    export JRE_HOME=${JAVA_HOME}/jre
    export CLASSPATH=.:${JAVA_HOME}/lib:${JRE_HOME}/lib
    export PATH=${JAVA_HOME}/bin:$PATH

第一段代码标红部分是刚才jdk解压的路径，这个一定不要写错。

（注：编辑.bashrc时，百度有的教程会用vim命令，vim是一个编辑器，如果有人用vim编辑.bashrc时，进到文本里面，键盘敲“ i ”，左下角显示“插入”标识，这时可以进行文本编辑，编辑结束后键盘按Esc，左下角“插入”标识消失，键盘敲入“ ：”冒号，然后输入“ wq ”回车，退出vim编辑器，回到了终端界面。我当时进入到vim后就不知道怎么退出来了，所以这里说一下）

在终端输入：

    source ~/.bashrc

使.bashrc生效，如果提示权限问题，就在命令前面加上sudo

## 四，安装完成，验证java是否配置完成 ##
终端输入

    java -version

![请输入图片描述][6]


  [1]: https://images.shiguangping.com/images/Linux%E5%AD%A6%E4%B9%A0%E4%B9%8B~ubuntu%E5%AE%89%E8%A3%85jdk%E5%8F%8A%E9%85%8D%E7%BD%AE%E7%8E%AF%E5%A2%83%E5%8F%98%E9%87%8F/%E5%9B%BE1.png
  [2]: https://images.shiguangping.com/images/Linux%E5%AD%A6%E4%B9%A0%E4%B9%8B~ubuntu%E5%AE%89%E8%A3%85jdk%E5%8F%8A%E9%85%8D%E7%BD%AE%E7%8E%AF%E5%A2%83%E5%8F%98%E9%87%8F/%E5%9B%BE2.png
  [3]: https://images.shiguangping.com/images/Linux%E5%AD%A6%E4%B9%A0%E4%B9%8B~ubuntu%E5%AE%89%E8%A3%85jdk%E5%8F%8A%E9%85%8D%E7%BD%AE%E7%8E%AF%E5%A2%83%E5%8F%98%E9%87%8F/%E5%9B%BE3.png
  [4]: https://images.shiguangping.com/images/Linux%E5%AD%A6%E4%B9%A0%E4%B9%8B~ubuntu%E5%AE%89%E8%A3%85jdk%E5%8F%8A%E9%85%8D%E7%BD%AE%E7%8E%AF%E5%A2%83%E5%8F%98%E9%87%8F/%E5%9B%BE4.png
  [5]: https://images.shiguangping.com/images/Linux%E5%AD%A6%E4%B9%A0%E4%B9%8B~ubuntu%E5%AE%89%E8%A3%85jdk%E5%8F%8A%E9%85%8D%E7%BD%AE%E7%8E%AF%E5%A2%83%E5%8F%98%E9%87%8F/%E5%9B%BE5.png
  [6]: https://images.shiguangping.com/images/Linux%E5%AD%A6%E4%B9%A0%E4%B9%8B~ubuntu%E5%AE%89%E8%A3%85jdk%E5%8F%8A%E9%85%8D%E7%BD%AE%E7%8E%AF%E5%A2%83%E5%8F%98%E9%87%8F/%E5%9B%BE6.png

这时，出现了java的版本号及相关信息，说明jdk配置成功，此时jdk已经安装完成。

按照上面一步一步的安装，就不会出现其他问题。

这里注意配置环境变量的路径。

有的人会问，jdk安装到其它路径可不可以，不安装到系统路径下，这个估计是没问题，但是我没尝试。推荐按照我这个步骤和路径安装，这样不会出现路径写错。

以上就是我今天在ubuntu上安装jdk环境的所有步骤。有问题可以加我qq或者微信，互相交流，因为我也是小白一只。

ubuntu安装eclipse,python和pycharm教程稍后更新。
本教程文章由李炎编写，发布在本人的个人博客shiguangping.com