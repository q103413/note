---
description: 宝塔域名迁移到目标服务器
---

# 宝塔迁移自建服务器

宝塔域名迁移到目标服务器 11.22.33.44 NGINX CDN申请测试二级域名->添加ns解析 migration.xxx.com migration.xxx.com cname xxx.vip.

安装代码发布工具

Nginx配置文件目录 /usr/local/nginx1.23/conf/vhosts

Nginx资源文件目录 /data/front/miss-daohang

目标服务器开scp端口 linux scp -P xxxx /var/www/test.php root@11.22.33.44:/data/front/

window 打开git输入命令：

&#x20;cd C:/work/xxx.zip scp -P 22 xxx.zip root@11.22.33.44:/data/front/

输入密码：xxxxx

解压 unzip xxxzip

Nginx添加配置文件 /usr/local/nginx1.23/conf/vhosts

`root@ip-1:/usr/local/nginx1.23/conf/vhosts# touch miss-navigation-page.conf`&#x20;

`直接访问静态文件`&#x20;

`server { listen 80; server_name migration.kjishaunembng.com; location / { root /data/front/miss-navigation-page; index index.html index.htm; }`

`}`

通过CDN添加端口访问，好处是以后方便添加域名（不用修改NGINX配置文件） 本质上是域名对应端口 miss\_navigation\_port 26185 server { listen 26185;

## server\_name migration.kjishaunembng.com;

```
server_name  localhost	
 location / {
    root   /data/front/miss-navigation-page;
    index  index.html index.htm;
}
```

}

CDN开启了HTTPS，源站是否必须配置HTTPS？

总之，客户端访问CDN节点和CDN节点访问源站，是两段不同的链路。 CDN开启HTTPS对客户端访问CDN节点有效，源站配置HTTPS对CDN节点访问源站有效。 因此，CDN开启HTTPS，是由阿里云控制台中对源站信息的端口配置决定的，不强制要求源站配置HTTPS。 不过，建议CDN和源站都开启HTTPS，确保全链路的安全。

portal.miss88.com portal.kjishaunembng.com

root@ip-17:/usr/local/nginx1.23/conf/vhosts# touch miss-navigation-page-redirect.conf

代理访问其他域名&#x20;

`server { listen 80; server_name portal.xxx.com; return 301 https://migration.xxx.com$request_uri; }`

nginx -s reload：reload 命令会重新加载配置文件，而nginx服务不会中断，服务启动，文件即加载成功。
