title: 内网穿透工具-Frp

date: 2020-10-6 09:27

categories:

- Tools

tags: 

- 内网穿透
- Frp

---

准备工作：

- 具有固定公网IP的主机（我使用的是阿里云的VPS）
- 主角：**Frp**工具，[点击下载](https://github.com/fatedier/frp/releases)
- 内网中的主机，也就是我们最终需要在外网访问的内网中的主机



---

### 配置服务端（VPS中）

下载地址：[https://github.com/fatedier/frp/releases](https://github.com/fatedier/frp/releases)

**下载Frp：**

```bash
wget https://github.com/fatedier/frp/releases/download/v0.34.0/frp_0.34.0_linux_amd64.tar.gz
```

>*下载速度不理想可以先下载到本地，再上传到Linux服务器上*
>
>1、从服务器上下载文件
>
>```bash
>scp username@servername:/path/filename /var/www/local_dir（本地目录）
>```
>
>2、上传本地文件到服务器
>
>```bash
>scp /path/filename username@servername:/path
>```
>
>3、从服务器下载整个目录
>
>```bash
>scp -r username@servername:/var/www/remote_dir/（远程目录） /var/www/local_dir（本地目录）
>```
>
>4、上传目录到服务器
>
>```bash
>scp  -r local_dir username@servername:remote_dir
>```

**解压：**

```bash
tar -zxvf frp_0.34.0_linux_amd64.tar.gz
```

**进入目录：**

![image-20201006125017260](https://images.shiguangping.com/imgs/20201006125017.png)

目录中主要文件：

- `frps`服务端
- `frps.ini`服务端配置文件

- `frpc`客户端
- `frpc.ini`客户端配置文件

**修改`frps.ini`：**

```bash
vim frps.ini
```

配置文件：

```ini
[common]
# 服务端端口号
bind_port = 7000

# 如果你想要用 frp 穿透访问内网中的网站（例如路由器设置页面）
# 则必须要设置以下两个监听端口，不设置则不会开启这项功能
vhost_http_port = 80
vhost_https_port = 443

# 连接认证token(可选)
token = 12345678

# 则你将 test.example.com 解析到服务端后，可以使用此域名来访问客户端对应的 http
subdomain_host = liyan.run

# 自定义404 页面，要用绝对路径哦！
# custom_404_page = /root/frp_0.27.0_linux_amd64/404.html

# 仪表盘端口，只有设置了才能使用仪表盘（即后台）
dashboard_port = 81
# 仪表盘访问的用户名密码，如果不设置，则默认都是 admin
dashboard_user = admin
dashboard_pwd = admin
```

**启动frps：**

```bash
screen -S frps ./frps -c frps.ini
```

>安装screen：
>
>```bash
>yum install screen
>```

使用快捷键Ctrl+A D(即按住Ctrl，依次再按A,D)，使程序在后台运行。



### 配置客户端

在内网主机中下载Frp，或通过本地上传：

```bash
wget https://github.com/fatedier/frp/releases/download/v0.34.0/frp_0.34.0_linux_amd64.tar.gz
```

**同服务端操作一样，解压后进入目录：**

**修改`frpc.ini`：**

配置文件：

```ini
[common]
# 服务端ip或域名(域名需要将域名解析到VPS)
server_addr = frp.liyan.run
# 服务端端口号
server_port = 7000
# 服务端设置的token
token = 12345678
admin_addr = 127.0.0.1
admin_port = 7400

[ssh]
type = tcp
local_port = 22
# 远程访问的端口号
remote_port = 6000
use_encryption = true
use_compression = true
```

**启动frpc：**

```bash
screen -S frpc ./frpc -c frpc.ini
```



### 测试

```bash
ssh -p 6000 liyan@frp.liyan.run
```

可以正常登录到内网主机，说明内网穿透成功。

---

详细的文档：

中文：[https://gitee.com/dengweiwen/frp](https://gitee.com/dengweiwen/frp)

英文：[https://github.com/fatedier/frp](https://github.com/fatedier/frp)

