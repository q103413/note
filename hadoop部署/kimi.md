# Hadoop 3.1.4 完全分布式集群 · 一步一命令实操笔记  
> 基于泰迪《第 2 章》PDF 整理，面向 0-1 搭建场景。  
> **目标**：4-VM 集群（1×master + 3×slave）在 **2 小时内**跑起来！

---

## 0 环境速查
| 硬件     | 最低    | 推荐          |
| -------- | ------- | ------------- |
| 内存     | 8 GB    | 16 GB         |
| 硬盘剩余 | 100 GB  | 150 GB        |
| CPU      | i5 4 核 | i7/RYZEN 8 核 |

---

## 1 软件包一次下齐
| 软件               | 版本    | 文件名                             |
| ------------------ | ------- | ---------------------------------- |
| VMware Workstation | ≥15     | `VMware-workstation-full-15.x.exe` |
| CentOS 7           | 7.8     | `CentOS-7-x86_64-DVD-2003.iso`     |
| JDK                | 1.8u281 | `jdk-8u281-linux-x64.rpm`          |
| Hadoop             | 3.1.4   | `hadoop-3.1.4.tar.gz`              |
| Xshell             | 7       | `Xshell7.exe`                      |

---

## 2 拓扑与 IP（抄表即可）
```
master   192.168.128.130  NameNode + ResourceManager
slave1   192.168.128.131  DataNode + NodeManager
slave2   192.168.128.132  DataNode + NodeManager
slave3   192.168.128.133  DataNode + NodeManager
```

---

## 3 30 分钟装好 master
1. **VMware → 新建虚拟机**  
   - 典型 → 稍后安装系统 → Linux / CentOS 7 64-bit  
   - 名称：`master`；位置：`E:\VMs\master`  
   - 2 CPU + 2 GB RAM + 20 GB 硬盘  
   - 网络：**NAT**  
   - 挂载 ISO → 开机 → **Minimal Install**  
   - Root 密码：`123456`

2. **固定 IP**（防止重启后漂移）  
   ```bash
   vi /etc/sysconfig/network-scripts/ifcfg-ens33
   ```
   ```properties
   BOOTPROTO=static
   ONBOOT=yes
   IPADDR=192.168.128.130
   NETMASK=255.255.255.0
   GATEWAY=192.168.128.2
   DNS1=8.8.8.8
   ```
   ```bash
   systemctl restart network
   ```

---

## 4 本地 YUM 源（离线也能装）
```bash
# 挂载 ISO
mount /dev/sr0 /media
# 禁用官方源
cd /etc/yum.repos.d
rename .repo .repo.bak *
# 创建本地源
cat > local.repo <<EOF
[local]
name=CentOS-Local
baseurl=file:///media
gpgcheck=0
enabled=1
EOF
yum clean all && yum makecache
```

---

## 5 一键装必备工具
```bash
yum install -y vim zip openssh-server openssh-clients ntp
```

---

## 6 装 JDK 并写环境变量
```bash
rpm -ivh jdk-8u281-linux-x64.rpm
cat >> /etc/profile <<EOF
export JAVA_HOME=/usr/java/jdk1.8.0_281-amd64
export PATH=\$JAVA_HOME/bin:\$PATH
export HADOOP_HOME=/usr/local/hadoop-3.1.4
export PATH=\$HADOOP_HOME/bin:\$HADOOP_HOME/sbin:\$PATH
EOF
source /etc/profile
```

---

## 7 Hadoop 解压 + 7 个配置文件（照抄即可）
```bash
tar -zxf hadoop-3.1.4.tar.gz -C /usr/local
cd /usr/local/hadoop-3.1.4/etc/hadoop
```

| 文件                | 关键行                                                       |
| ------------------- | ------------------------------------------------------------ |
| **core-site.xml**   | `<value>hdfs://master:8020</value>`                          |
| **hadoop-env.sh**   | `export JAVA_HOME=/usr/java/jdk1.8.0_281-amd64`              |
| **yarn-env.sh**     | 同上                                                         |
| **mapred-site.xml** | `<value>yarn</value>`                                        |
| **yarn-site.xml**   | `<name>yarn.resourcemanager.hostname</name><value>master</value>` |
| **workers**         | 写入：<br>`slave1`<br>`slave2`<br>`slave3`                   |
| **hdfs-site.xml**   | `<value>dfs.replication=3</value>`                           |

---

## 8 克隆 3 台 slave（5 分钟）
1. 关闭 master  
2. VMware → 管理 → 克隆 → **完整克隆**  
   - 名称：`slave1` / `slave2` / `slave3`  
   - 路径：`E:\VMs\slaveX`  
3. **每台开机后改 IP + 主机名**  
   ```bash
   # slave1 示例
   sed -i 's/130/131/g' /etc/sysconfig/network-scripts/ifcfg-ens33
   hostnamectl set-hostname slave1
   reboot
   ```

---

## 9 SSH 免密（master 执行）
```bash
ssh-keygen -t rsa -P '' -f ~/.ssh/id_rsa
ssh-copy-id slave1 && ssh-copy-id slave2 && ssh-copy-id slave3
```

---

## 10 时间同步（NTP）
| 节点   | 命令                                            |
| ------ | ----------------------------------------------- |
| master | `systemctl start ntpd && systemctl enable ntpd` |
| slaves | `ntpdate master && systemctl start ntpd`        |

---

## 11 一键启动集群
```bash
# 仅第一次
hdfs namenode -format
# 启动
start-dfs.sh
start-yarn.sh
# 验证
jps
```
- master 应看到：`NameNode` `ResourceManager`  
- slaves 应看到：`DataNode` `NodeManager`

---

## 12 Web UI 速览
| 服务       | 地址                |
| ---------- | ------------------- |
| HDFS       | http://master:9870  |
| YARN       | http://master:8088  |
| JobHistory | http://master:19888 |

---

## 13 懒人脚本（启停一条命令）
```bash
# ~/bin/cluster.sh
case $1 in
  start) start-dfs.sh && start-yarn.sh ;;
  stop)  stop-yarn.sh && stop-dfs.sh ;;
  *) echo "Usage: cluster.sh start|stop" ;;
esac
chmod +x ~/bin/cluster.sh
```

---

## 14 常见坑 & 急救
| 现象               | 快速修复                            |
| ------------------ | ----------------------------------- |
| jps 无 NameNode    | 重新格式化 & 检查 `core-site.xml`   |
| slaves 无 DataNode | `ping slave1` & `ssh slave1`        |
| 端口被占用         | `netstat -tulnp | grep 9870` 杀进程 |

---

## 15 小结：一句话流程
> **装 VMware → 创 master → 固定 IP → 配 YUM → 装 JDK → 解压 Hadoop → 改 7 个文件 → 克隆 3 台 → SSH 免密 → 同步时间 → 一键启动 → 浏览器 9870/8088 看界面！**

**完整脚本 & 模板已上传：**  
[https://github.com/yourname/hadoop-cluster-template](https://github.com/yourname/hadoop-cluster-template)

**Happy Hadooping!**