# 1、本地开发调试

## 环境设置

修改域名映射到本地回环地址，命令sudo vim /etc/hosts

```
127.0.0.1 superwash.shop
```

## 代码改动
本地开发调试需要处理以下两个地方

![输入图片说明](https://images.gitee.com/uploads/images/2020/0712/112218_2f3cab18_7723489.png "屏幕截图.png")
![输入图片说明](https://images.gitee.com/uploads/images/2020/0712/112231_c0b7ee3e_7723489.png "屏幕截图.png")

## 常用命令

```
// 安装本地依赖
npm install

// 本地运行
npm run start
```

# 2、打包发布

## 打包Web代码

```
// 安装本地依赖
npm install
// 编译生成生产包
npm run build

// 压缩包
zip dist

// 拷贝文件到服务器
scp ~/Workspace/superwash_operation_web/superwash.zip root@106.52.154.130:/root/web


// 服务器更新代码
* 1./root/web/superwash  进入此目录
* 2.删除之前上面目录的所有文件
* 3.解压前端项目打包文件 unzip superwash.zip  项目发布完毕！
```


### 登陆系统
可以在本地通过 ssh root@106.52.154.130输入密码登陆，也可以在腾讯云的管理后台登陆

### 后台代码更新

小程序后台代码 superwash 发布文档

```
1.项目根目录下执行命令 bee pack -be GOOS=linux -be GOARCH=amd64 获得 super_wash.tar.gz 文件
2.登录linux文件服务器,目录 /data/web/super_wash 下 ，删除原来所有文件(日志有必要可以保留，cert, nohup.out不要删)，
3.super_wash.tar.gz 文件上传至linux服务器第二步的目录下 ，scp ./super_wash.tar.gz root@120.79.216.28:/data/newwash/super_wash.tar.gz
4.解压 tar -xzvf super_wash.tar.gz 文件
5.执行命令 ps -ef | grep super_wash 获取super_wash pid ，然后kill -9 pid 掉
6.在 /root/web/super_wash 目录下执行 nohup ./super_wash & ,项目部署完毕
7.如果宕机 就直接执行第6步 就可以重启服务了
```


web后台代码 super_wash_bg 发布文档

```
1.项目根目录下执行命令 bee pack -be GOOS=linux -be GOARCH=amd64 获得 super_wash_bg.tar.gz 文件
2.登录linux文件服务器,目录 /data/web/super_wash_bg 下 ，删除原来所有文件(日志有必要可以保留)，
3.super_wash_bg.tar.gz 文件上传至linux服务器第二步的目录下 ，scp ./super_wash_bg.tar.gz root@120.79.216.28:/data/web/super_wash_bg/super_wash_bg.tar.gz
4.解压 tar -xzvf super_wash_bg.tar.gz 文件
5.执行命令 ps -ef | grep super_wash_bg 获取super_wash_bg pid ，然后kill -9 pid 掉
6.在 /data/web/super_wash_bg 目录下执行 nohup ./super_wash_bg & ,项目部署完毕
7.如果宕机 就直接执行第6步 就可以重启服务了
```


前端项目部署：

```
1./root/web/superwash 进入此目录
2.删除之前上面目录的所有文件
3.解压前端项目打包文件 unzip superwash.zip 项目发布完毕！
```


### nginx 配置
安装位置 /usr/local/nginx


```
到对应目录下 /usr/local/nginx/sbin
启动命令： ./nginx
关闭命令： ./nginx -s stop
重启命令： ./nginx -s  reload

```

### 查看日志
后台的日志在当前项目的目录下 nohup.out 这个文件中， 或者有一个/data/web/log/superwash/log.txt 也是日志查看的


# 3.常用命令帮助文档
```
可以简单用scp 命令来实现

查看scp帮助：sup -h

输出信息如下：usage: scp [-12346BCEpqrv] [-c cipher] [-F ssh_config] [-i identity_file]  [-l limit] [-o ssh_option] [-P port] [-S program][[user@]host1:]file1 … [[user@]host2:]file2

OPTIONS：

-v  显示进度。可以用来查看连接、认证、或是配置错误

-P 选择端口

-r 复制目录

1、从本地将文件传输到服务器
scp[本地文件的路径]   [服务器用户名]@[服务器地址]:[服务器上存放文件的路径]

scp /Users/mac/Desktop/test.txt root@192.168.1.1:/root

2、从本地将文件夹传输到服务器
scp -r[本地文件的路径]   [服务器用户名]@[服务器地址]:[服务器上存放文件的路径]

scp -r /Users/mac/Desktop/test root@192.168.1.1:/root

3、将服务器上的文件传输到本地
scp [服务器用户名]@[服务器地址]:[服务器上存放文件的路径]   [本地文件的路径]

scp root@192.168.1.1:/root/default/test.txt /Users/mac/Desktop

4、将服务器上的文件夹传输到本地
scp -r [服务器用户名]@[服务器地址]:[服务器上存放文件的路径]   [本地文件的路径]

scp -r root@192.168.1.1:/root/default/test /Users/mac/Desktop
```


```
删除当前目录下的文件

1.rm -rf *
#最经典的方法，删除当前目录下的所有类型的文件

4.rm-f `find . -type f`
#删除全部普通文件

删除指定目录下的文件
1.rm -f 指定目录*
#最经典的方法，删除指定目录下的所有类型的文件
4.rm-f `find 指定目录 -type f`
#删除指定目录下的全部普通文件
```


```
1.从服务器复制文件到本地：

scp root@192.168.1.100:/data/test.txt /home/myfile/
补充：多文件拷贝
scp root@192.168.1.100:/data/\{test1.txt,test2.cpp,test3.bin,test.*\} /home/myfile/
root@192.168.1.100   root是目标服务器（有你需要拷贝文件的服务器）的用户名，192.168.1.100是IP地址，后面紧跟的 “：” 不要忘记，/data/test.txt（多文件还有test1.txt，test2.cpp，test3.bin，test.a，test.c等） 是目标服务器中你要拷贝文件的地址，接一个空格，后面的 /home/myfile/ 是本地接收文件的地址。

2.从服务器复制文件夹到本地：

scp -r root@192.168.1.100:/data/ /home/myfile/
只需在前面加 -r 即可，就可以拷贝整个文件夹。

3.从本地复制文件到服务器：

scp /home/myfile/test.txt root@192.168.1.100:/data/
补充：多文件拷贝
scp /home/myfile/test1.txt test2.cpp test3.bin test.* root@192.168.1.100:/data/
 

4.从本地复制文件夹到服务器：

scp -r /home/myfile/ root@192.168.1.100:/data/
```
