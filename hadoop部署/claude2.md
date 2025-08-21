# Hadoop集群搭建与配置学习笔记

## 1. 环境准备

### 1.1 硬件配置要求
- **内存**: 至少8GB
- **硬盘**: 可用容量至少100GB  
- **CPU**: Intel i5以上多核处理器（建议八核及以上）

### 1.2 软件版本清单

| 软件 | 版本 | 安装包名称 | 备注 |
|------|------|-----------|------|
| Linux OS | CentOS 7.8 | CentOS-7-x86_64-DVD-2003.iso | 64位 |
| JDK | 1.8+ | jdk-8u281-linux-x64.rpm | 64位 |
| VMware | 15 | VMware-workstation-full-15.5.7-17171714.exe | 虚拟机软件 |
| Hadoop | 3.1.4 | hadoop-3.1.4.tar.gz | 已编译安装包 |
| SSH工具 | Xshell 5 | Xme5.exe | 远程连接虚拟机 |

### 1.3 集群架构设计

```
集群拓扑结构：
┌─────────────┐    ┌─────────────┐    ┌─────────────┐    ┌─────────────┐
│   Master    │    │   Slave1    │    │   Slave2    │    │   Slave3    │
│192.168.128.130│  │192.168.128.131│  │192.168.128.132│  │192.168.128.133│
│             │    │             │    │             │    │             │
│ NameNode    │    │ DataNode    │    │ DataNode    │    │ DataNode    │
│ResourceMgr  │    │ NodeManager │    │ NodeManager │    │ NodeManager │
└─────────────┘    └─────────────┘    └─────────────┘    └─────────────┘
```

## 2. 虚拟机安装与配置

### 2.1 VMware虚拟机创建步骤

1. **启动VMware Workstation** → 选择"创建新的虚拟机"
2. **选择典型模式** → 下一步
3. **安装选项** → 选择"稍后安装操作系统"
4. **操作系统** → 选择"Linux" → "CentOS 7 64位"
5. **虚拟机命名** → 名称："master"，位置："E:\VMware\master"
6. **磁盘设置** → 最大磁盘大小：20GB，选择"拆分成多个文件"
7. **硬件配置** → 自定义硬件 → 指定ISO文件位置

### 2.2 CentOS 7.8安装流程

#### 基本配置步骤：
1. **语言设置**: English (United States)
2. **时区设置**: Asia/Shanghai
3. **磁盘分区**: 使用默认自动分区
4. **网络配置**: 主机名设置为"master"
5. **用户设置**: 设置root密码为"123456"

### 2.3 网络配置（固定IP设置）

#### 修改网络配置文件：
```bash
# 编辑网络配置文件
vim /etc/sysconfig/network-scripts/ifcfg-ens33

# 配置内容：
BOOTPROTO=static
ONBOOT=yes
IPADDR=192.168.128.130
NETMASK=255.255.255.0
GATEWAY=192.168.128.2
DNS1=8.8.8.8
```

#### 重启网络服务：
```bash
service network restart
ip addr  # 验证IP设置
```

### 2.4 远程连接配置（Xshell）

#### VMware网络设置：
1. 编辑 → 虚拟网络编辑器
2. 选择VMnet8 → 子网IP设置为：192.168.128.0

#### Xshell连接配置：
- **主机**: 192.168.128.130
- **用户名**: root
- **密码**: 123456

## 3. 系统环境配置

### 3.1 YUM本地源配置

```bash
# 进入yum配置目录
cd /etc/yum.repos.d

# 备份原有配置文件
mv CentOS-Base.repo CentOS-Base.repo.bak
mv CentOS-Debuginfo.repo CentOS-Debuginfo.repo.bak
mv CentOS-fasttrack.repo CentOS-fasttrack.repo.bak
mv CentOS-Vault.repo CentOS-Vault.repo.bak

# 修改本地源配置
vim CentOS-Media.repo
# 修改内容：
# baseurl=file:///media/
# gpgcheck=0
# enabled=1

# 挂载本地源
mount /dev/sr0 /media

# 清理缓存并测试
yum clean all
```

### 3.2 常用软件安装

```bash
# 安装必要软件包
yum install -y vim zip openssh-server openssh-clients
```

## 4. Java环境安装

### 4.1 JDK安装步骤

```bash
# 上传JDK到/opt目录
# 使用Ctrl+Alt+F进行文件传输

# 安装JDK
cd /opt
rpm -ivh jdk-8u281-linux-x64.rpm

# 验证安装
java -version
```

## 5. Hadoop集群配置

### 5.1 Hadoop安装

```bash
# 解压Hadoop到指定目录
tar -zxf hadoop-3.1.4.tar.gz -C /usr/local

# 进入配置目录
cd /usr/local/hadoop-3.1.4/etc/hadoop
```

### 5.2 核心配置文件修改

#### 5.2.1 core-site.xml
```xml
<configuration>
    <property>
        <name>fs.defaultFS</name>
        <value>hdfs://master:8020</value>
    </property>
    <property>
        <name>hadoop.tmp.dir</name>
        <value>/var/log/hadoop/tmp</value>
    </property>
</configuration>
```

#### 5.2.2 hadoop-env.sh
```bash
export JAVA_HOME=/usr/java/jdk1.8.0_281-amd64
```

#### 5.2.3 yarn-env.sh
```bash
export JAVA_HOME=/usr/java/jdk1.8.0_281-amd64
```

#### 5.2.4 mapred-site.xml
```xml
<configuration>
    <property>
        <name>mapreduce.framework.name</name>
        <value>yarn</value>
    </property>
    <property>
        <name>mapreduce.jobhistory.address</name>
        <value>master:10020</value>
    </property>
    <property>
        <name>mapreduce.jobhistory.webapp.address</name>
        <value>master:19888</value>
    </property>
    <property>
        <name>yarn.app.mapreduce.am.env</name>
        <value>HADOOP_MAPRED_HOME=${HADOOP_HOME}</value>
    </property>
    <property>
        <name>mapreduce.map.env</name>
        <value>HADOOP_MAPRED_HOME=${HADOOP_HOME}</value>
    </property>
    <property>
        <name>mapreduce.reduce.env</name>
        <value>HADOOP_MAPRED_HOME=${HADOOP_HOME}</value>
    </property>
</configuration>
```

#### 5.2.5 yarn-site.xml
```xml
<configuration>
    <property>
        <name>yarn.resourcemanager.hostname</name>
        <value>master</value>
    </property>
    <property>
        <name>yarn.resourcemanager.address</name>
        <value>${yarn.resourcemanager.hostname}:8032</value>
    </property>
    <property>
        <name>yarn.resourcemanager.scheduler.address</name>
        <value>${yarn.resourcemanager.hostname}:8030</value>
    </property>
    <property>
        <name>yarn.resourcemanager.webapp.address</name>
        <value>${yarn.resourcemanager.hostname}:8088</value>
    </property>
    <property>
        <name>yarn.nodemanager.aux-services</name>
        <value>mapreduce_shuffle</value>
    </property>
    <property>
        <name>yarn.nodemanager.resource.memory-mb</name>
        <value>2048</value>
    </property>
    <property>
        <name>yarn.scheduler.minimum-allocation-mb</name>
        <value>512</value>
    </property>
    <property>
        <name>yarn.scheduler.maximum-allocation-mb</name>
        <value>4096</value>
    </property>
</configuration>
```

#### 5.2.6 hdfs-site.xml
```xml
<configuration>
    <property>
        <name>dfs.namenode.name.dir</name>
        <value>file:///data/hadoop/hdfs/name</value>
    </property>
    <property>
        <name>dfs.datanode.data.dir</name>
        <value>file:///data/hadoop/hdfs/data</value>
    </property>
    <property>
        <name>dfs.namenode.secondary.http-address</name>
        <value>master:50090</value>
    </property>
    <property>
        <name>dfs.replication</name>
        <value>3</value>
    </property>
</configuration>
```

#### 5.2.7 workers文件
```
slave1
slave2
slave3
```

#### 5.2.8 hosts文件配置
```bash
# 编辑hosts文件
vim /etc/hosts

# 添加以下内容：
192.168.128.130 master
192.168.128.131 slave1
192.168.128.132 slave2
192.168.128.133 slave3
```

## 6. 虚拟机克隆与配置

### 6.1 克隆操作步骤

1. **右键master虚拟机** → 管理 → 克隆
2. **选择克隆源** → 虚拟机中的当前状态
3. **克隆类型** → 创建完整克隆
4. **设置名称** → slave1, slave2, slave3
5. **选择位置** → E:\VMware\slave1等

### 6.2 从节点配置修改

#### 每个从节点需要修改：

```bash
# 修改IP地址
vim /etc/sysconfig/network-scripts/ifcfg-ens33
# slave1: IPADDR=192.168.128.131
# slave2: IPADDR=192.168.128.132  
# slave3: IPADDR=192.168.128.133

# 重启网络
service network restart

# 修改主机名
hostnamectl set-hostname slave1  # 对应修改为slave2, slave3

# 重启系统
reboot
```

## 7. SSH免密登录配置

### 7.1 在master节点执行

```bash
# 生成密钥对
ssh-keygen -t rsa
# 连续按3次Enter键

# 复制公钥到各个节点
ssh-copy-id root@master
ssh-copy-id root@slave1
ssh-copy-id root@slave2
ssh-copy-id root@slave3

# 验证免密登录
ssh slave1
ssh slave2
ssh slave3
```

## 8. 时间同步服务配置

### 8.1 安装NTP服务

```bash
# 在所有节点安装NTP
yum install -y ntp

# 关闭防火墙
systemctl stop firewalld
systemctl disable firewalld
```

### 8.2 主节点配置

```bash
# 编辑NTP配置文件
vim /etc/ntp.conf

# 注释掉原有server行，添加：
server 127.127.1.0
fudge 127.127.1.0 stratum 10

# 启动NTP服务
systemctl start ntpd
systemctl enable ntpd
systemctl status ntpd  # 查看状态
```

### 8.3 从节点配置

```bash
# 编辑NTP配置文件
vim /etc/ntp.conf

# 注释掉原有server行，添加：
server master

# 同步时间
ntpdate master

# 启动NTP服务
systemctl start ntpd
systemctl enable ntpd
```

## 9. 环境变量配置

### 9.1 在所有节点配置

```bash
# 编辑环境变量文件
vim /etc/profile

# 添加以下内容：
export JAVA_HOME=/usr/java/jdk1.8.0_281-amd64
export HADOOP_HOME=/usr/local/hadoop-3.1.4
export PATH=$PATH:$JAVA_HOME/bin:$HADOOP_HOME/bin:$HADOOP_HOME/sbin

# 使配置生效
source /etc/profile
```

## 10. 集群启动与管理

### 10.1 格式化NameNode

```bash
# 仅在master节点执行一次
hdfs namenode -format
```

### 10.2 启动集群

```bash
# 在master节点执行
cd /usr/local/hadoop-3.1.4/sbin

# 启动HDFS
./start-dfs.sh

# 启动YARN
./start-yarn.sh

# 启动JobHistoryServer
./mr-jobhistory-daemon.sh start historyserver
```

### 10.3 验证集群状态

```bash
# 在各个节点执行jps查看进程
# Master节点应该显示：
# - NameNode
# - ResourceManager
# - SecondaryNameNode
# - JobHistoryServer

# Slave节点应该显示：
# - DataNode  
# - NodeManager
```

### 10.4 关闭集群

```bash
# 在master节点执行
./stop-yarn.sh
./stop-dfs.sh
./mr-jobhistory-daemon.sh stop historyserver
```

## 11. Web监控界面

### 11.1 监控端口说明

| 服务 | Web接口 | 默认端口 |
|------|---------|----------|
| NameNode | http://master:9870 | 9870 |
| ResourceManager | http://master:8088 | 8088 |
| JobHistoryServer | http://master:19888 | 19888 |

### 11.2 本地hosts配置

在Windows系统的 `C:\Windows\System32\drivers\etc\hosts` 文件中添加：
```
192.168.128.130 master
192.168.128.131 slave1
192.168.128.132 slave2
192.168.128.133 slave3
```

## 12. 常见问题解决

### 12.1 虚拟机网络问题
- 检查VMware网络配置
- 确认防火墙已关闭
- 验证IP地址配置正确

### 12.2 SSH连接问题
- 确认openssh-server已安装
- 检查网络连通性
- 验证用户名密码正确

### 12.3 集群启动失败
- 检查配置文件语法
- 确认JAVA_HOME路径正确
- 验证hosts文件配置
- 查看日志文件排错

## 13. 总结

本学习笔记涵盖了Hadoop完全分布式集群的完整搭建过程，包括：
- 虚拟机环境准备与配置
- Linux系统安装与网络配置  
- Java环境安装
- Hadoop核心配置文件修改
- 集群节点克隆与配置
- SSH免密登录配置
- 时间同步服务配置
- 集群启动管理与监控

通过这些步骤，可以成功搭建一个1主3从的Hadoop完全分布式集群环境，为后续的大数据开发和学习奠定基础。