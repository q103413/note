



板状态：运行中
 队列状态：运行中
=========================面板账户信息===========================

 面板版本: v1.2.7
 外网面板地址: http://8.138.162.227:16158/b27db6
 内网面板地址: http://172.28.231.197:16158/b27db6
 username: f00763a1
 password: 0e79f927

=========================面板注意事项===========================

 【云服务器】请在安全组放行 16158 端口
 面板工具命令： xp

================================================================
安装花费时间: 87 秒
安装日志路径: /data/nginx/conf/xp-install.log 



shopxo

后台管理地址: http://a.rmb520.com/admingduxgf.php

后台账号: admin

后台密码: 123456





个人myshopxo

后台管理地址: http://ai.rmb520.com/adminebenm5.php?s=index/index.html

http://ai.rmb520.com/

后台账号: admin

后台密码: 123456

shopxo git token

d6427ae534072579dbf1da754215982b





beike

http://bei.ni520.com/

##### 设置后台账号密码

后台账号: root@guangda.work

后台密码: dwjommgnipadwp3f



dbcart 

|       网站名称 | DBCart多语言商城系统 |
| -------------: | -------------------- |
| 系统管理员帐号 | admin                |
| 系统管理员密码 | 123456               |





dbshop

http://db.rmb520.com/

http://db.rmb520.com/admin

|       网站名称 | DBShop商城系统 |
| -------------: | -------------- |
| 系统管理员帐号 | admin          |
| 系统管理员密码 | 123456         |

http://dbs.rmb520.com/

http://dbs.rmb520.com/admin



creb

http://cr.rmb520.com/

http://cr.rmb520.com/admin/

后台账号: admin

后台密码: 123456



git 

# docker

https://docker.m.daocloud.io

docker.1ms.run

mysql

docker search docker.1ms.run/mysql

docker pull docker.1ms.run/mysql

docker pull docker.1ms.run/mysql:5.7



#启动
docker start mysql

#新建
docker run -d  --name mysql  -p 3306:3306  -e TZ=Asia/Shanghai  -e MYSQL_ROOT_PASSWORD=123456 -v /data/mysql/data:/var/lib/mysql   -v /data/mysql/conf:/etc/mysql/conf.d  -v /data/mysql/log:/var/log/mysql   -v /data/mysql/init:/docker-entrypoint-initdb.d  -d 5107



docker run --name mysql57 -e MYSQL_ROOT_PASSWORD=my-secret-pw -d 5107

docker exec -it mysql57 mysql -u root -p

GRANT ALL PRIVILEGES ON *.* TO 'root'@'%' IDENTIFIED BY 'root';

docker run --name mysql57 -e MYSQL_ROOT_PASSWORD=my-secret-pw -v mysql57_data:/var/lib/mysql -d mysql:5.7



docker volume create mysql57_data

docker run --name mysql57 -e MYSQL_ROOT_PASSWORD=my-secret-pw -v mysql57_data:/var/lib/mysql -d 5107


docker run --name mysql57 -e MYSQL_ROOT_PASSWORD=my-secret-pw -v mysql57_data:/var/lib/mysql -d mysql:5.7

sudo docker run -p 3306:3306 --name mysql -v /data/mysql/log:/var/log/mysql -v /data/mysql/data:/var/lib/mysql -v /data/mysql/conf:/etc/mysql -e MYSQL_ROOT_PASSWORD=root -d 5107333e08a8

CREATE USER 'maple123' IDENTIFIED BY '500384qqq';

GRANT ALL PRIVILEGES ON *.* TO 'maple123';

FLUSH PRIVILEGES;



#启动
docker start mysql

#新建
docker run -d \
  --name mysql57  \
  -p 3306:3306 \
  -e TZ=Asia/Shanghai \
  -e MYSQL_ROOT_PASSWORD=123456 \
  -v /home/hm/mysql/data:/var/lib/mysql \
  -v /home/hm/mysql/conf:/etc/mysql/conf.d \
  -v /home/hm/mysql/init:/docker-entrypoint-initdb.d \
  --network hm-net\
  mysql



docker run --name some-mysql -e MYSQL_ROOT_PASSWORD=my-secret-pw -e MYSQL_TCP_PORT=3306 -p 3306:3306 -d 5107



```dockerfile
docker run docker.m.daocloud.io/hello-world

docker run docker.1ms.run/hello-world


docker search docker.1ms.run/gitbook

docker search docker.1ms.run/nginx

docker run --name nginx-test -p 80:80 -d nginx

docker run --name nginx-test -p 80:80 -d b52e

docker cp b366980d69a5:/etc/nginx/nginx.conf /data/nginx

docker cp b366980d69a5:/etc/nginx/conf.d/default.conf /data/nginx/conf/


docker run --name nginx-config -p 80:80 -v /data/nginx/nginx.conf:/etc/nginx/nginx.conf  -v /data/nginx/logs:/var/log/nginx  -v /data/nginx/html:/usr/share/nginx/html  -v /data/nginx/conf:/etc/nginx/conf.d  --privileged=true -d b52e
```



mkdir -p /data/minio/config

mkdir -p /data/minio/config

docker run -d -p 9001:9000 -p 9092:9092 --name minio -e "MINIO_ACCESS_KEY=minioadmin" -e "MINIO_SECRET_KEY=minioadmin" -v /data/minio/data:/data -v /data/minio/config:/root/.minio minio/minio server /data --console-address ":9000" -address ":9090"

```nginx
server {
    listen 80;
    server_name example.com;
    location / {
        proxy_pass  http://172.28.231.197;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
	}
}
```



# server

8.138.162.227

172.28.231.197





sudo apt install nodejs=12 npm
