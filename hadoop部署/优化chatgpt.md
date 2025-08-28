我已通读了你上传的《Hadoop集群任务1安装及配置虚拟机置-实操文档.md》。整体框架很好，已经包含了图表、截图和操作命令，但存在以下问题：

- 部分 **步骤编号混乱**（如“步骤2”出现两次）。
- **操作流程有重复描述**，可以合并优化。
- 缺少 **统一的命令汇总区块**，学习者查找不便。
- **验证与总结部分不完整**，缺少关键检查点。
- **格式不够统一**，有些地方用中文叙述，有些地方用命令，排版可优化。

下面是我帮你整理、完善和优化后的结构提纲（保持 Markdown 语法 + 适合 Typora 阅读）：

------

# Hadoop集群搭建与配置 - 任务1 安装及配置虚拟机

## 📊 集群架构图

（保留你的 Mermaid 图表，推荐只留一份简洁清晰的拓扑结构，其他合并到附录）

------

## 🛠 环境准备

### 硬件要求

- 内存 ≥ 8GB
- 硬盘 ≥ 100GB
- CPU ≥ Intel i5 多核（推荐 8 核）

### 软件清单

| 软件     | 版本       | 安装包                             | 说明           |
| -------- | ---------- | ---------------------------------- | -------------- |
| Linux OS | CentOS 7.8 | CentOS-7-x86_64-DVD-2003.iso       | 64位操作系统   |
| JDK      | 1.8+       | jdk-8u281-linux-x64.rpm            | Java开发环境   |
| VMware   | 15+        | VMware-workstation-full-15.5.7.exe | 虚拟机软件     |
| Hadoop   | 3.1.4      | hadoop-3.1.4.tar.gz                | 大数据处理框架 |
| SSH工具  | Xshell 8   | Xme8.exe                           | 远程连接工具   |

------

## 🔧 第一步：创建 Master 虚拟机

### 1.1 安装 VMware & 新建虚拟机

1. 安装 **VMware Workstation**（一路下一步）。
2. 选择 **创建新的虚拟机** → 模式：典型。
3. 操作系统类型：**Linux / CentOS 7 64位**。
4. 命名：`master`，路径：`E:\VMware\master`。
5. 磁盘：20GB（拆分存储）。
6. 网络：NAT 模式。
7. 挂载 ISO：选择 `CentOS-7-x86_64-DVD-2003.iso`。

### 1.2 安装 CentOS 系统

- 选择 *Install CentOS 7*。
- 语言：English (United States)。
- 时区：Asia/Shanghai。
- 主机名：`master`。
- Root 密码：`123456`。
- 分区：默认自动。
- 完成后重启，输入 root 密码进入系统。

------

## 🔧 第二步：配置固定 IP

### 修改网络配置

```bash
vi /etc/sysconfig/network-scripts/ifcfg-ens33
```

修改内容：

```ini
ONBOOT=yes
BOOTPROTO=static
IPADDR=192.168.128.130
NETMASK=255.255.255.0
GATEWAY=192.168.128.2
DNS1=8.8.8.8
```

### 生效与验证

```bash
service network restart
ip addr   # 确认IP为192.168.128.130
```

------

## 🔧 第三步：配置远程连接（Xshell）

1. VMware → 编辑 → 虚拟网络编辑器 → VMnet8 子网IP：`192.168.128.0`。
2. 打开 **Xshell** → 新建会话：
   - Host：192.168.128.130
   - User：root
   - Password：123456

测试是否能成功连接。

------

## 🔧 第四步：配置 YUM 源 & 安装常用软件

### 配置本地源

```bash
cd /etc/yum.repos.d
mv CentOS-Base.repo CentOS-Base.repo.bak
vi CentOS-Media.repo
```

修改内容：

```ini
baseurl=file:///media
gpgcheck=0
enabled=1
```

### 挂载 ISO & 清理缓存

```bash
mount /dev/sr0 /media
yum clean all
yum list
```

### 安装常用工具

```bash
yum install -y vim zip openssh-server openssh-clients
```

------

## 🛡️ 常见问题与解决方案

### 1. 虚拟机无法联网

```bash
service network status
service network restart
ip addr show
```

### 2. ISO 挂载失败

- 确认虚拟机设置中 **CD/DVD 驱动器已勾选“已连接”**。

------

## ✅ 验证清单

-  Master 虚拟机能成功开机并进入 CentOS。
-  IP 固定为 192.168.128.130。
-  可以通过 Xshell 远程连接。
-  YUM 源可用，能正常安装软件。

------

## 📝 总结

本任务完成了 **虚拟机创建、操作系统安装、固定 IP 配置、远程连接、YUM 源配置与软件安装**，为后续 Hadoop 分布式集群搭建打下基础。

------

👉 我建议把 **截图 + Mermaid 图表** 都保留，这样文档既有直观演示，也有结构化流程图，便于复习和演示。

要不要我帮你把 **后续任务（比如 JDK 安装、Hadoop 安装、SSH免密、时间同步）** 的文档也设计一个统一模板，这样整套文档风格保持一致？