---
description: 宝塔域名迁移到目标服务器
---

# 宝塔迁移自建服务器

## 一、需求

* 宝塔域名迁移到目标服务器（配置Nginx、CDN，迁移资源文件）。
* 迁移两类域名，一类域名访问落地页(landing.com)，另一类域名导航页(navigation.com)重定向到落地页。
* 测试，申请二级域名（migration.landing.com migration.navigation.com）。

## 二、准备

* Nginx配置文件目录 /usr/local/nginx1.23/conf/vhosts/
* Nginx资源文件目录 /data/front/
* 用SCP命令传文件（后续安装代码发布工具）

## 三、开始

1. Nginx添加配置文件 /usr/local/nginx1.23/conf/vhosts

`进入对应目录：cd /usr/local/nginx1.23/conf/vhosts`&#x20;

`创建配置文件：touch pro-navigation-page.conf`&#x20;

```
// Nginx配置(落地页静态文件)
server { 
    listen 80; 
    server_name migration.landing.com; 
    location / { 
        root /data/front/pro-navigation-page; 
        index index.html index.htm; 
    }
}
```

2. 进阶：通过CDN添加端口访问，好处是以后方便添加域名（不用修改NGINX配置文件）， 本质上是CDN源站对应端口，源站IP:8888

```
// CDN域名直接对应源站端口
server {
    listen       8888;
    server_name  localhost	
     location / {
        root   /data/front/miss-navigation-page;
        index  index.html index.htm;
    }
   
}
```

3. 传送资源文件

目标服务器开scp端口，默认22&#x20;

linux :

`scp -P xxxx /var/www/test.php root@11.22.33.44:/data/front/`

window : 打开git：

```
// Some code
scp -P 22 C:/work/xxx.zip root@11.22.33.44:/data/front/
```

最后输入目标服务器密码：xxxxx

解压 unzip xxx.zip

4. 代理访问其他域名（重定向）

`server {`&#x20;

&#x20;   `listen 80;`&#x20;

&#x20;   `server_name portal.navigation.com;`&#x20;

&#x20;   `return 301 https://migration.xxx.com$request_uri;`&#x20;

`}`

portal.yyy.com portal.xxx.com

`root@ip-17:/usr/local/nginx1.23/conf/vhosts# touch miss-navigation-page-redirect.conf`

5. 重启Nginx

nginx -s reload：reload 命令会重新加载配置文件，而nginx服务不会中断，服务启动，文件即加载成功。

### 知识点：

CDN开启了HTTPS，源站是否必须配置HTTPS？

总之，客户端访问CDN节点和CDN节点访问源站，是两段不同的链路。 CDN开启HTTPS对客户端访问CDN节点有效，源站配置HTTPS对CDN节点访问源站有效。 因此，CDN开启HTTPS，是由阿里云控制台中对源站信息的端口配置决定的，不强制要求源站配置HTTPS。 不过，建议CDN和源站都开启HTTPS，确保全链路的安全。

### scp命令：

1、从服务器上下载文件 scp username@servername:/path/filename /var/www/local\_dir（本地目录）

scp root@192.168.0.101:/var/www/test.txt 把192.168.0.101上的/var/www/test.txt的文件下载到/var/www/local\_dir（本地目录）

2、上传本地文件到服务器 scp /path/filename username@servername:/path

例如scp /var/www/test.php root@192.168.0.101:/var/www/ 把本机/var/www/目录下的test.php文件上传到192.168.0.101这台服务器上的/var/www/目录中

通常情况下, ssh的默认端口都会自定义

```
// 指定端口号的方法:
# scp -P port file_name user@ip:/dir_name
```

