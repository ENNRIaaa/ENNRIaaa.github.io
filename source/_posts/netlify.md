title: 静态页面托管服务-Netlify

date: 2020-10-07 16:38

categories:

- Tools

tags:

- Netlity

---

Github Pages已经凉凉了[Facepalm]

[Netlify](https://app.netlify.com/)是一个提供静态网站托管的服务平台，可以持续部署，能够将托管在 GitHub，GitLab 等网站上的 Jekyll，Hexo，Hugo 等代码自动编译并生成静态网站。

<!--more-->

---

[https://app.netlify.com/](https://app.netlify.com/)

![image-20201007165401301](https://images.shiguangping.com/imgs/20201007165401.png)

选择使用GitHub账号登录，点击`New site from Git`：

![image-20201007165823158](https://images.shiguangping.com/imgs/20201007165823.png)

根据自己的托管平台，选择代码GitHub、GitLab或者BitBucket（这里以GitHub为例）：

![image-20201007165948780](https://images.shiguangping.com/imgs/20201007165948.png)

点击GitHub之后会弹出一个让你授权的窗口，给 Netlify 授权后，就会自动读取你 GitHub 的仓库：

![image-20201007170042761](https://images.shiguangping.com/imgs/20201007170042.png)

选择仓库后，Netlify 会自动识别到 Hexo，并填入相关信息，这时候只要无脑点击 `Deploy site`就可以：

![image-20201007170528878](https://images.shiguangping.com/imgs/20201007170528.png)

构建成功后设置自定义域名：

![image-20201007171404020](https://images.shiguangping.com/imgs/20201007171404.png)

填写域名：

![image-20201007171434450](https://images.shiguangping.com/imgs/20201007171434.png)

点击核实后添加域名，之后可以配置HTTPS。

---

![image-20201007171806439](https://images.shiguangping.com/imgs/20201007171806.png)

当站点部署完成之后，可以自动化部署，只要 push 了代码，就会自动构建，在上面的页面可以查看到每次构建的信息。

---

**使用Netlify部署Gitbook**

在 build command 里，填入：`npm install -g gitbook-cli && gitbook install && gitbook build`

在 publish 目录填入： `_book/` 

