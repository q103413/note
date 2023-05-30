# Linux常用命令

服务第一，技术第二 docker ps -a 进入容器 docker attach id docker exec -it 243c32535da7 /bin/bash docker rm id

mysql 运行容器 docker run -it xxx /bin/bash docker run -itd --name mysql-test -p 3306:3306 -e MYSQL\_ROOT\_PASSWORD=123456 mysql

docker start <容器 ID> docker stop <容器 ID>

1）lsof -i:端口号，即可查看某一端口的占用情况， 2)netstat -lntup | grep 端口号 用于查看指定端口号的进程情况，

ps aux --sort -pmem|head

find / -name 'tomcat7' -type d find / -name 'server.xml' -print

dpkg --print-architecture arch unzip tar xvf file

SecretKey xfas6FPQ4sad8s37

参数启动 ./Yearning run --push "IP地址" -port "8000" nohup command &

初始化成功! 用户名: admin 密码:Yearning\_admin 请通过./Yearning run 运行, 默认地址:http://8.212.47.250:8000

systemctl status firewalld firewall-cmd --state systemctl start firewalld firewall-cmd --zone=public --add-port=8000/tcp --permanent firewall-cmd --reload netstat -ntlp\
netstat -ntulp |grep 8000\
systemctl stop firewalld

sudo systemctl restart service

curl curl -d

find / -type f -name "_.log" | xargs grep "ERROR" find . -name "_.log" | xargs grep "error"

一、查看 nginx 安装目录 ps -ef | grep nginx

二、查看配置文件 nginx.conf 路径 nginx -t 这条命令也可以用于检查配置文件是否正确。

## 从 / 根目录下查找文件名为 nginx.conf 的文件

find / -name nginx.conf

sed 's/要被取代的字串/新的字串/g' testfile sed -n '5,10p' filename

tail -f/n xxx.file
