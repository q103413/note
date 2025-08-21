好的，我根据文档内容帮你整理了一篇以实操为主的 **Hadoop集群搭建与配置学习笔记（Markdown版）**，内容精简且步骤清晰，方便你在实验环境中快速实践。

------

# Hadoop集群搭建与配置学习笔记

## 1. 集群环境说明

Hadoop集群有三种模式：

- **单机模式**：直接在一台机器运行，调试用。
- **伪分布式模式**：在一台机器上模拟多节点。
- **完全分布式模式**：多台机器组成真实集群（生产推荐）。

本笔记以 **完全分布式（1主3从）** 为例。

**最低硬件要求：**

- 内存 ≥ 8GB
- 硬盘 ≥ 100GB
- CPU ≥ i5（建议8核以上）

**软件版本：**

- CentOS 7.8
- JDK 1.8+
- Hadoop 3.1.4
- VMware Workstation 15
- Xshell/Xmanager

------

## 2. 虚拟机环境搭建

### 2.1 安装 VMware Workstation

- 下载并安装 `VMware-workstation-full-15.5.7.exe`。

### 2.2 创建 CentOS 虚拟机

1. 新建虚拟机 → 选择 **典型安装**。
2. 操作系统选择 **CentOS 7 64位**。
3. 磁盘分配：**20GB**，拆分为多个文件。
4. 选择 ISO 镜像：`CentOS-7-x86_64-DVD-2003.iso`。
5. 主机名设置为 **master**，root 密码 `123456`。
6. 完成安装并重启，登录成功看到 `[root@master ~]#`。

### 2.3 配置固定 IP

编辑网卡配置：

```bash
vim /etc/sysconfig/network-scripts/ifcfg-ens33
```

修改为：

```
ONBOOT=yes
BOOTPROTO=static
IPADDR=192.168.128.130
NETMASK=255.255.255.0
GATEWAY=192.168.128.2
DNS1=8.8.8.8
```

重启网络：

```bash
service network restart
ip addr
```

### 2.4 使用 Xshell 远程连接

- 配置会话：主机 = `192.168.128.130`，用户名 `root`，密码 `123456`。
- 连接成功后可用命令操作虚拟机。

### 2.5 配置 YUM 源 & 常用工具

1. 挂载 ISO：

```bash
mount /dev/sr0 /media
```

1. 修改本地源：

```bash
cd /etc/yum.repos.d
mv CentOS-Base.repo CentOS-Base.repo.bak
vim CentOS-Media.repo   # baseurl=file:///media/
```

1. 清理缓存并安装软件：

```bash
yum clean all
yum install -y vim zip openssh-server openssh-clients
```

------

## 3. Hadoop 环境配置

### 3.1 安装 JDK

上传并安装：

```bash
rpm -ivh jdk-8u281-linux-x64.rpm
java -version   # 验证
```

### 3.2 安装 Hadoop

```bash
tar -zxf hadoop-3.1.4.tar.gz -C /usr/local/
cd /usr/local/hadoop-3.1.4/etc/hadoop
```

修改以下配置文件：

#### `core-site.xml`

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

#### `hadoop-env.sh`

```bash
export JAVA_HOME=/usr/java/jdk1.8.0_281-amd64
```

#### `mapred-site.xml`

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
</configuration>
```

#### `yarn-site.xml`

```xml
<configuration>
  <property>
    <name>yarn.resourcemanager.hostname</name>
    <value>master</value>
  </property>
  <property>
    <name>yarn.resourcemanager.webapp.address</name>
    <value>master:8088</value>
  </property>
</configuration>
```

#### `hdfs-site.xml`

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
    <name>dfs.replication</name>
    <value>3</value>
  </property>
</configuration>
```

#### `workers`

```
slave1
slave2
slave3
```

------

## 4. 集群搭建

### 4.1 克隆虚拟机

- 克隆 master → 生成 slave1、slave2、slave3。
- 修改各自 IP & 主机名。
- 在 master 上 `ping slaveX` 验证连通性。

### 4.2 配置 SSH 免密登录

```bash
ssh-keygen -t rsa   # 3次回车
ssh-copy-id slave1
ssh-copy-id slave2
ssh-copy-id slave3
```

### 4.3 配置时间同步

```bash
yum install -y ntp
systemctl start ntpd
systemctl enable ntpd
ntpdate master    # 在各从节点同步
```

------

## 5. 启动与验证

### 5.1 格式化 NameNode

```bash
hdfs namenode -format
```

### 5.2 启动集群

```bash
cd /usr/local/hadoop-3.1.4
sbin/start-dfs.sh
sbin/start-yarn.sh
```

### 5.3 验证进程

```bash
jps
```

master 节点应包含 NameNode、ResourceManager 等。
 slave 节点应包含 DataNode、NodeManager。

------

## 6. 集群监控

浏览器访问：

- **HDFS**: [http://master:9870](http://master:9870/)
- **YARN**: [http://master:8088](http://master:8088/)
- **JobHistory**: [http://master:19888](http://master:19888/)

------

## 7. 总结

1. VMware + CentOS 搭建 Linux 环境。
2. 配置固定 IP、YUM 源、常用工具。
3. 安装 JDK & Hadoop 并修改配置文件。
4. 克隆节点，配置 SSH 免密 & 时间同步。
5. 格式化 NameNode → 启动集群 → Web 界面验证。

------

要不要我帮你把这份笔记再扩展成 **一份分步骤操作手册（带命令行速查表）**，方便你直接拿来实验？