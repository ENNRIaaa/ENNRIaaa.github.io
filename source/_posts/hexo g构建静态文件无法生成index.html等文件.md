title: hexo g构建静态文件无法生成index.html等文件
date: 2018-06-16 04:12:26
toc: true

---
### 问题现象

安装好`nodejs`,`git`,`HEXO`之后,在GitHub上重新克隆hexo源文件到本地,然后通过`hexo c`,`hexo g`命令后,`public`文件夹内没有`index.html`等文件。

### 检查npm插件

```shell
npm ls --depth 0
```

通过命令查看缺少的插件,终端会提示很多`npm ERR!`



### 解决方法

```shell
npm install hexo-generator-archive --save
```

安装后重新`hexo c`,`hexo g`即可.



### 题外话

我今天通过上述方法解决了没有`index.html`的问题，但是生成的`index.html`是空的。后来发现`themes`文件夹里面的主题文件夹是空的，之后重新下载主题文件放进去就好了。

