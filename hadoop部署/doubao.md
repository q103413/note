# Hadoop 完全分布式集群搭建学习笔记（实操版）

## 一、集群环境基础认知

### 1. 集群类型划分

Hadoop 集群环境分为三种类型，各有不同适用场景：

- **单机环境**：在单台机器上运行，无分布式文件系统，直接读取本地文件，适合初步了解 Hadoop 基础功能。
- **伪分布式环境**：在单台机器上模拟多节点集群，可用于学习 Hadoop 的分布式原理。
- **完全分布式环境**：在多台机器上组建真实分布式集群，贴近生产环境，是本次学习的重点。

### 2. 硬件与软件准备

- **硬件最低配置**：内存至少 8GB，硬盘可用容量至少 100GB，CPU 为 Intel i5 以上多核（建议八核及以上）。

- 必备软件及版本

  ：

  | 软件         | 版本       | 安装包名称                                  | 备注             |      |
  | ------------ | ---------- | ------------------------------------------- | ---------------- | ---- |
  | Linux OS     | CentOS 7.8 | CentOS-7-x86_64-DVD-2003.iso                | 64 位            |      |
  | JDK          | 1.8+       | jdk-8u281-linux-x64.rpm                     | 64 位            |      |
  | VMware       | 15         | VMware-workstation-full-15.5.7-17171714.exe | 虚拟机软件       |      |
  | Hadoop       | 3.1.4      | hadoop-3.1.4.tar.gz                         | 已编译好的安装包 |      |
  | SSH 连接工具 | 5          | Xme5.exe                                    | 远程连接虚拟机   |      |

### 3. 集群拓扑结构

本次搭建的 Hadoop 完全分布式集群为 1 主 3 从架构：

- 主节点（master）：IP 为 192.168.128.130，运行 NameNode、SecondaryNameNode、ResourceManager。
- 从节点（slave1）：IP 为 192.168.128.131，运行 DataNode、NodeManager。
- 从节点（slave2）：IP 为 192.168.128.132，运行 DataNode、NodeManager。
- 从节点（slave3）：IP 为 192.168.128.133，运行 DataNode、NodeManager。

## 二、虚拟机安装与基础配置（以 master 为例）

### 1. 创建 Linux 虚拟机

1. 安装 VMware：双击安装包 VMware-workstation-full-15.5.7-17171714.exe，选择安装目录，输入产品序列号完成安装。
2. 新建虚拟机：打开 VMware，选择 “创建新的虚拟机”，选 “典型（推荐）” 模式。
3. 操作系统设置：选择 “稍后安装操作系统”，客户机操作系统选 “Linux”，版本为 “CentOS 7 64 位”。
4. 命名与存储：虚拟机名称为 “master”，安装位置设为 “E:\VMware\master”。
5. 磁盘配置：最大磁盘大小 20GB，选择 “将虚拟磁盘拆分成多个文件”。
6. 自定义硬件：在 “CD/DVD（IDE）” 中选择 CentOS-7-x86_64-DVD-2003.iso 镜像文件，完成设置。

### 2. 安装 CentOS 系统

1. 启动虚拟机：选择 “开启此虚拟机”，在安装界面选 “Install CentOS 7”。
2. 语言设置：选择 “English（United States）”，点击 “Continue”。
3. 时间配置：在 “DATE & TIME” 中选择 “Asia/Shanghai”。
4. 安装位置：默认自动分区，点击 “Done”。
5. 主机名设置：在 “NETWORK & HOST NAME” 中设为主机名 “master”，点击 “Begin Installation”。
6. 密码设置：root 密码设为 “123456”（需连续确认两次），完成安装后重启。
7. 登录系统：输入用户名 “root” 和密码 “123456”，出现 “[root@master ~]#” 即登录成功。

### 3. 固定 IP 配置

1. 查看网络配置文件：`vim /etc/sysconfig/network-scripts/ifcfg-ens33`。
2. 修改配置：将 ONBOOT 改为 “yes”，BOOTPROTO 改为 “static”，添加 IPADDR=192.168.128.130、NETMASK=255.255.255.0、GATEWAY=192.168.128.2、DNS1=114.114.114.114。
3. 重启网络：`service network restart`，用`ip addr`查看 IP 是否设置成功。

### 4. 远程连接（Xshell）

1. 安装 Xmanager：双击 Xme5.exe，选择安装位置完成安装。
2. 配置虚拟网络：在 VMware “编辑” 菜单中打开 “虚拟网络编辑器”，将 VMnet8 的子网 IP 改为 “192.168.128.0”。
3. 新建 Xshell 会话：名称为 “master”，主机为 192.168.128.130，用户身份验证输入 root 和密码 123456。
4. 连接虚拟机：选中会话 “master” 点击 “连接”，接受并保存主机密钥完成连接。

### 5. 配置本地 YUM 源及安装软件

1. 进入 YUM 目录：`cd /etc/yum.repos.d`。
2. 禁用默认源：将 CentOS-Base.repo 等文件重命名为带.bak 的备份文件。
3. 修改本地源：`vim CentOS-Media.repo`，将 baseurl 改为 “file:///media/”，gpgcheck 改为 0，enabled 改为 1。
4. 挂载镜像：`mount /dev/sr0 /media`，若失败需在 VMware 中勾选 CD/DVD “已连接”。
5. 清理缓存：`yum clean all`。
6. 安装软件：`yum install -y vim zip openssh-server openssh-clients`。

## 三、Hadoop 集群核心配置

### 1. 安装 JDK

1. 上传安装包：通过 Xshell 文件传输将 jdk-8u281-linux-x64.rpm 上传至 /opt 目录。
2. 安装 JDK：`rpm -ivh /opt/jdk-8u281-linux-x64.rpm`。
3. 验证安装：`java -version`，显示 1.8.0_281 版本即成功。

### 2. 安装与配置 Hadoop

1. 上传并解压：将 hadoop-3.1.4.tar.gz 上传至 /opt，解压到 /usr/local：`tar -zxf /opt/hadoop-3.1.4.tar.gz -C /usr/local`。
2. 进入配置目录：`cd /usr/local/hadoop-3.1.4/etc/hadoop`。
3. 修改 7 个核心配置文件：
   - **core-site.xml**：配置 fs.defaultFS 为 hdfs://master:8020，hadoop.tmp.dir 为 /var/log/hadoop/tmp。
   - **hadoop-env.sh**：设置`export JAVA_HOME=/usr/java/jdk1.8.0_281-amd64`。
   - **yarn-env.sh**：设置`export JAVA_HOME=/usr/java/jdk1.8.0_281-amd64`。
   - **mapred-site.xml**：配置 mapreduce.framework.name 为 yarn，以及 jobhistory 相关地址。
   - **yarn-site.xml**：配置 yarn.resourcemanager.hostname 为 master，以及各类服务端口。
   - **workers**：添加 slave1、slave2、slave3。
   - **hdfs-site.xml**：配置 NameNode 和 DataNode 存储路径，副本数为 3。

### 3. 克隆从节点（slave1/2/3）

1. 克隆虚拟机：关闭 master，右键 “管理”→“克隆”，选择 “虚拟机中的当前状态” 和 “创建完整克隆”，命名为 slave1，位置设为 E:\VMware\slave1。
2. 修改 slave1 配置：
   - 修改 IP：`vim /etc/sysconfig/network-scripts/ifcfg-ens33`，设 IPADDR=192.168.128.131。
   - 重启网络：`service network restart`。
   - 修改主机名：`hostnamectl set-hostname slave1`，重启虚拟机。
3. 验证连接：在 master 中`ping slave1`，能收到回复即成功。
4. 重复上述步骤克隆 slave2（IP:192.168.128.132）和 slave3（IP:192.168.128.133）。

## 四、集群协同配置

### 1. SSH 免密码登录（master 节点）

1. 生成密钥对：`ssh-keygen -t rsa`，连续按 3 次 Enter。
2. 复制公钥：`ssh-copy-id`到 master、slave1、slave2、slave3。
3. 验证：`ssh slave1`无需密码登录，说明配置成功。

### 2. 时间同步服务

1. 安装 NTP：所有节点执行`yum install -y ntp`。
2. 配置 master（NTP 主节点）：`vim /etc/ntp.conf`，注释 server 开头行，添加`server 127.127.1.0`和`fudge 127.127.1.0 stratum 10`。
3. 配置从节点：`vim /etc/ntp.conf`，注释 server 开头行，添加`server master`。
4. 关闭防火墙：`systemctl stop firewalld`和`systemctl disable firewalld`。
5. 启动服务：
   - master：`systemctl start ntpd`和`systemctl enable ntpd`，用`systemctl status ntpd`查看状态。
   - 从节点：先`ntpdate master`同步时间，再启动服务。

## 五、集群启动与验证

### 1. 配置环境变量

1. 所有节点修改

   ```
   /etc/profile
   ```

   ，添加：

   bash

   

   

   

   

   

   ```bash
   export HADOOP_HOME=/usr/local/hadoop-3.1.4
   export PATH=$PATH:$HADOOP_HOME/bin:$HADOOP_HOME/sbin
   ```

2. 生效配置：`source /etc/profile`。

### 2. 格式化与启动集群

1. 格式化 NameNode：在 master 执行`hdfs namenode -format`，出现 “successfully formatted” 即成功（仅执行一次）。
2. 启动集群：
   - 启动 HDFS：`start-dfs.sh`。
   - 启动 YARN：`start-yarn.sh`。

### 3. 验证集群状态

1. 进程检查：各节点执行`jps`，master 应显示 NameNode 等进程，从节点应显示 DataNode 等进程。
2. Web 监控：
   - HDFS 监控：http://master:9870。
   - YARN 监控：http://master:8088。
   - 日志监控：http://master:19888。

### 4. 关闭集群

在 master 执行：

- 关闭 YARN：`stop-yarn.sh`。
- 关闭 HDFS：`stop-dfs.sh`。

## 总结

本笔记详细记录了 Hadoop 完全分布式集群的搭建过程，从虚拟机安装、系统配置到集群协同设置，重点突出实操步骤。关键在于确保各节点网络互通、配置文件正确、SSH 免密登录和时间同步，这些是集群稳定运行的基础。通过 Web 监控和进程检查可验证集群状态，为后续 HDFS 操作和 MapReduce 编程奠定基础。