# Hadoop完全分布式集群搭建实操指南

## 环境准备

### 硬件要求
- **内存**: 至少8GB
- **硬盘**: 可用容量至少100GB  
- **CPU**: Intel i5以上多核处理器（建议八核及以上）

### 软件版本清单
| 软件 | 版本 | 安装包名称 | 备注 |
|------|------|-----------|------|
| Linux OS | CentOS 7.8 | CentOS-7-x86_64-DVD-2003.iso | 64位 |
| JDK | 1.8+ | jdk-8u281-linux-x64.rpm | 64位 |
| VMware | 15 | VMware-workstation-full-15.5.7-17171714.exe | 虚拟机软件 |
| Hadoop | 3.1.4 | hadoop-3.1.4.tar.gz | 已编译安装包 |
| SSH连接工具 | Xshell 5 | Xme5.exe | 远程连接虚拟机 |

### 集群拓扑结构
- **主节点(master)**: NameNode + ResourceManager + JobHistoryServer
- **从节点(slave1~3)**: DataNode + NodeManager

## 第一部分：VMware虚拟机安装配置

### 1.1 创建Linux虚拟机

**步骤1**: 安装VMware Workstation
```bash
# 双击安装包，按向导完成安装
VMware-workstation-full-15.5.7-17171714.exe
```

**步骤2**: 创建虚拟机
1. 打开VMware → "创建新的虚拟机" → 选择"典型(推荐)"
2. 选择"稍后安装操作系统"
3. 客户机操作系统: Linux，版本: CentOS 7 64位
4. 虚拟机名称: `master`，位置: `E:\VMware\master`
5. 磁盘大小: 20GB，选择"将虚拟磁盘拆分成多个文件"

**步骤3**: 配置硬件
- 单击"自定义硬件" → "新CD/DVD(IDE)" 
- 选择"使用ISO映像文件" → 指定CentOS镜像路径

### 1.2 安装CentOS系统

**启动安装**:
```bash
# 开启虚拟机，选择 Install CentOS 7
# 语言选择: English (United States)
```

**系统配置**:
1. **时区设置**: Asia/Shanghai
2. **磁盘分区**: 使用默认自动分区
3. **网络配置**: 
   - 主机名设置为 `master`
   - 开启网络连接
4. **Root密码**: 设置为 `123456`

### 1.3 配置固定IP

**查看网络配置文件**:
```bash
# 重启网卡服务
service network restart

# 查看网络配置
cat /etc/sysconfig/network-scripts/ifcfg-ens33
```

**修改网络配置**:
```bash
vim /etc/sysconfig/network-scripts/ifcfg-ens33
```

配置内容：
```bash
TYPE=Ethernet
PROXY_METHOD=none
BROWSER_ONLY=no
BOOTPROTO=static          # 改为static
DEFROUTE=yes
IPV4_FAILURE_FATAL=no
IPV6INIT=yes
IPV6_AUTOCONF=yes
IPV6_DEFROUTE=yes
IPV6_FAILURE_FATAL=no
IPV6_ADDR_GEN_MODE=stable-privacy
NAME=ens33
UUID=xxxxx
DEVICE=ens33
ONBOOT=yes               # 改为yes

# 添加以下配置
IPADDR=192.168.128.130   # 静态IP
NETMASK=255.255.255.0    # 子网掩码
GATEWAY=192.168.128.2    # 网关
DNS1=8.8.8.8            # DNS服务器
```

**重启网络服务**:
```bash
service network restart
ip addr  # 验证IP配置
```

### 1.4 远程连接配置

**配置VMware虚拟网络**:
1. VMware菜单 → "编辑" → "虚拟网络编辑器"
2. 选择VMnet8，修改子网IP为 `192.168.128.0`

**安装Xshell并连接**:
1. 安装Xme5.exe
2. 新建会话:
   - 名称: `master`
   - 主机: `192.168.128.130`
   - 用户名: `root`
   - 密码: `123456`

### 1.5 配置YUM源

**禁用在线YUM源**:
```bash
cd /etc/yum.repos.d/
mv CentOS-Base.repo CentOS-Base.repo.bak
mv CentOS-Debuginfo.repo CentOS-Debuginfo.repo.bak
mv CentOS-fasttrack.repo CentOS-fasttrack.repo.bak  
mv CentOS-Vault.repo CentOS-Vault.repo.bak
```

**配置本地YUM源**:
```bash
vim CentOS-Media.repo
```

修改内容：
```bash
[c7-media]
name=CentOS-$releasever - Media
baseurl=file:///media/
gpgcheck=0
enabled=1
```

**挂载光盘**:
```bash
# 确保VMware中CD/DVD已连接
mount /dev/sr0 /media
yum clean all
```

**安装常用软件**:
```bash
yum install -y vim zip openssh-server openssh-clients
```

## 第二部分：Java环境安装

### 2.1 上传JDK安装包
```bash
# 使用Xshell文件传输功能(Ctrl+Alt+F)
# 上传 jdk-8u281-linux-x64.rpm 到 /opt 目录
```

### 2.2 安装JDK
```bash
cd /opt
rpm -ivh jdk-8u281-linux-x64.rpm
```

### 2.3 验证安装
```bash
java -version
# 输出Java版本信息表示安装成功
```

## 第三部分：Hadoop集群配置

### 3.1 上传并解压Hadoop
```bash
# 上传hadoop-3.1.4.tar.gz到/opt目录
cd /opt
tar -zxf hadoop-3.1.4.tar.gz -C /usr/local/
```

### 3.2 修改配置文件

**进入配置目录**:
```bash
cd /usr/local/hadoop-3.1.4/etc/hadoop/
```

#### 3.2.1 core-site.xml
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

#### 3.2.2 hadoop-env.sh
```bash
# 修改JAVA_HOME路径
export JAVA_HOME=/usr/java/jdk1.8.0_281-amd64
```

#### 3.2.3 yarn-env.sh
```bash
# 取消注释并修改JAVA_HOME
export JAVA_HOME=/usr/java/jdk1.8.0_281-amd64
```

#### 3.2.4 mapred-site.xml
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

#### 3.2.5 yarn-site.xml
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
        <name>yarn.nodemanager.vmem-check-enabled</name>
        <value>false</value>
    </property>
</configuration>
```

#### 3.2.6 workers
```bash
slave1
slave2
slave3
```

#### 3.2.7 hdfs-site.xml
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

### 3.3 修改启动脚本

**编辑启动脚本**:
```bash
cd /usr/local/hadoop-3.1.4/sbin/

# 在start-dfs.sh和stop-dfs.sh开头添加
vim start-dfs.sh stop-dfs.sh
```
添加内容：
```bash
#!/usr/bin/env bash
HDFS_DATANODE_USER=root
HDFS_DATANODE_SECURE_USER=hdfs
HDFS_NAMENODE_USER=root
HDFS_SECONDARYNAMENODE_USER=root
```

```bash
# 在start-yarn.sh和stop-yarn.sh开头添加
vim start-yarn.sh stop-yarn.sh
```
添加内容：
```bash
#!/usr/bin/env bash
YARN_RESOURCEMANAGER_USER=root
YARN_NODEMANAGER_USER=root
```

### 3.4 配置hosts文件
```bash
vim /etc/hosts
```
添加：
```bash
192.168.128.130 master
192.168.128.131 slave1
192.168.128.132 slave2
192.168.128.133 slave3
```

## 第四部分：集群部署

### 4.1 克隆虚拟机

**克隆步骤**:
1. 右键master虚拟机 → "管理" → "克隆"
2. 选择"虚拟机中的当前状态" → "创建完整克隆"
3. 分别创建slave1、slave2、slave3

**修改各slave节点配置**:

**slave1配置**:
```bash
# 修改IP地址
vim /etc/sysconfig/network-scripts/ifcfg-ens33
IPADDR=192.168.128.131

# 修改主机名
hostnamectl set-hostname slave1

# 重启网络和系统
service network restart
reboot
```

**slave2配置**:
```bash
IPADDR=192.168.128.132
hostnamectl set-hostname slave2
service network restart
reboot
```

**slave3配置**:
```bash
IPADDR=192.168.128.133
hostnamectl set-hostname slave3
service network restart
reboot
```

### 4.2 配置SSH免密登录

**在master节点执行**:
```bash
# 生成密钥对
ssh-keygen -t rsa
# 连续按3次回车

# 复制公钥到各节点
ssh-copy-id master
ssh-copy-id slave1
ssh-copy-id slave2  
ssh-copy-id slave3

# 验证免密登录
ssh slave1
ssh slave2
ssh slave3
```

### 4.3 配置时间同步服务

**安装NTP服务**:
```bash
# 在所有节点执行
yum install -y ntp
```

**配置master为时间服务器**:
```bash
vim /etc/ntp.conf
```
注释掉server开头的行，添加：
```bash
server 127.127.1.0
fudge 127.127.1.0 stratum 10
```

**配置slave节点**:
```bash
# 在slave1,slave2,slave3上执行
vim /etc/ntp.conf
```
注释掉server开头的行，添加：
```bash
server master
```

**启动NTP服务**:
```bash
# 关闭防火墙(所有节点)
systemctl stop firewalld
systemctl disable firewalld

# 启动NTP服务
# master节点
systemctl start ntpd
systemctl enable ntpd

# slave节点先同步时间
ntpdate master
systemctl start ntpd  
systemctl enable ntpd
```

### 4.4 配置环境变量

**所有节点配置**:
```bash
vim /etc/profile
```
添加：
```bash
export JAVA_HOME=/usr/java/jdk1.8.0_281-amd64
export HADOOP_HOME=/usr/local/hadoop-3.1.4
export PATH=$PATH:$JAVA_HOME/bin:$HADOOP_HOME/bin:$HADOOP_HOME/sbin
```

**使配置生效**:
```bash
source /etc/profile
```

## 第五部分：启动集群

### 5.1 格式化NameNode
```bash
# 在master节点执行(只需执行一次)
hdfs namenode -format
```

### 5.2 启动集群
```bash
# 在master节点执行
cd /usr/local/hadoop-3.1.4/sbin/

# 启动HDFS
./start-dfs.sh

# 启动YARN  
./start-yarn.sh

# 启动JobHistoryServer
mapred --daemon start historyserver
```

### 5.3 验证集群状态
```bash
# 在各节点查看Java进程
jps

# master节点应显示:
# NameNode
# ResourceManager
# JobHistoryServer
# SecondaryNameNode

# slave节点应显示:
# DataNode
# NodeManager
```

### 5.4 Web界面监控

**修改本机hosts文件**:
```bash
# Windows: C:\Windows\System32\drivers\etc\hosts
# 添加以下内容:
192.168.128.130 master
192.168.128.131 slave1
192.168.128.132 slave2
192.168.128.133 slave3
```

**访问Web界面**:
- **HDFS监控**: http://master:9870
- **YARN监控**: http://master:8088  
- **作业历史**: http://master:19888

### 5.5 关闭集群
```bash
# 在master节点执行
mapred --daemon stop historyserver
./stop-yarn.sh
./stop-dfs.sh
```

## 常见问题及解决方案

### 问题1：格式化失败
```bash
# 清理数据目录
rm -rf /data/hadoop/
# 重新格式化
hdfs namenode -format
```

### 问题2：DataNode无法启动
```bash
# 检查防火墙状态
systemctl status firewalld
# 确保防火墙已关闭

# 检查SSH免密登录
ssh slave1
```

### 问题3：Web界面无法访问
```bash
# 检查端口监听
netstat -tlnp | grep :9870
# 确保本机hosts文件配置正确
```

## 实用命令总结

### 集群操作命令
```bash
# 启动集群
start-dfs.sh && start-yarn.sh
mapred --daemon start historyserver

# 停止集群  
mapred --daemon stop historyserver
stop-yarn.sh && stop-dfs.sh

# 查看集群状态
hdfs dfsadmin -report
yarn node -list

# 查看HDFS文件
hdfs dfs -ls /
hdfs dfs -mkdir /test
hdfs dfs -put file.txt /test/
```

### 日志查看
```bash
# Hadoop日志目录
cd /usr/local/hadoop-3.1.4/logs/

# 实时查看日志
tail -f hadoop-root-namenode-master.log
```

通过以上步骤，你就成功搭建了一个4节点的Hadoop完全分布式集群。记住要定期备份虚拟机快照，方便快速恢复环境！