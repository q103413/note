# 如何使用VMware搭建虚拟机超详细教程, 图文

有很多客户告知，在使用VM搭建虚拟机的时候，出现很多问题，如自己安装精简版本，阉割版本。如搭建好之后怎么设置都无法和局域网内其他的机器进行链接，网络不通等问题。

下面给大家带来的教程，完整的为您解决所有问题。

# **所需工具：**

**一、VMware Workstation Pro**

**二、系统镜像一枚（原装完整的iso，比如centos7）**

三、设置网络

打开 VMware --> Edit（编辑）--> VirtualNetworkEditor（虚拟网络编辑器），如图：

VMnet8：用于虚拟 NAT 网络下的虚拟交换机

![image-20231016020548273](http://img.an520.com/test/image-20231016020548273.png)

![img](http://img.an520.com/test/713744-20190729232910301-1368050577.png)



四、挂载宿主机

https://www.cnblogs.com/xiaobaiskill/p/11298236.html

#### 三、安装vm-tools (请用root用户执行)

- 3.1 安装vm-tools

```kotlin
yum install -y open-vm-tools open-vm-tools-desktop
```

- 3.2 挂载

```bash
# 1 查看共享的目录
vmware-hgfsclient
# www

# 2 创建hgfs 文件夹
mkdir -p /data

# 3 用vmhgfs-fuse命令挂载目录
vmhgfs-fuse .host:/ /mnt/hgfs
vmhgfs-fuse .host:/ /newmnt/

# 4 此刻 www 目录即 真正挂载到 虚拟机上了
ls /mnt/hgfs
# www

#四、软连接至/home 目录下
# ln -s /mnt/hgfs/www /home/www
ln -s /hgfs/vmware/data /
```

### 3. 挂载共享文件夹到Centos中

上面步骤设置完，建议先重启Centos，再进行下面操作哦~，不然有时候会很坑爹的，共享配置还没更新~

默认Vmware共享的文件夹存放在 /mnt/hgfs/ 目录下，但是仅仅通过上面步骤，还是无法找到共享出去的本地目录的，还需要进行Centos的挂载；
挂载命令：

#### 四、软连接至/home 目录下

```bash
# ln -s /mnt/hgfs/www /home/www
ln -s /hgfs/vmware/data /
```

https://blog.csdn.net/weixin_43493256/article/details/89295886

![image-20231025010348727](http://img.an520.com/test/image-20231025010348727.png)

systemctl restart network



systemctl restart  docker



## VMware虚拟机三种联网方法及原理



一、Brigde——桥接：默认使用VMnet0   1、原理：   Bridge  桥"就是一个主机，这个机器拥有两块网卡，分别处于两个局域网中，同时在"桥"上，运行着程序，让局域网A中的所有数据包原封不动的流入B，反之亦然。这样，局域网A和B就无缝的在链路层连接起来了，在桥接时，VMWare网卡和物理网卡应该处于同一IP网段  当然要保证两个局域网没有冲突的IP.   VMWare 的桥也是同样的道理，只不过，本来作为硬件的一块网卡，现在由VMWare软件虚拟了！当采用桥接时，VMWare会虚拟一块网卡和真正的物理网卡就行桥接，这样，发到物理网卡的所有数据包就到了VMWare虚拟机，而由VMWare发出的数据包也会通过桥从物理网卡的那端发出。   所以，如果物理网卡可以上网，那么桥接的软网卡也没有问题了，这就是桥接上网的原理了。  　   2、联网方式：   这一种联网方式最简单，在局域网内，你的主机是怎么联网的，你在虚拟机里就怎么连网。把虚拟机看成局域网内的另一台电脑就行了！   提示：主机网卡处在一个可以访问Internet的局域网中，虚拟机才能通过Bridge访问Internet。  

\`````````````````````````````````````````````````````````````````````````````````````````````````````````````````````   二、NAT——网络地址转换  ：默认使用VMnet8   1、原理：   NAT 是  Network  address  translate的简称。NAT技术应用在internet网关和路由器上，比如192.168.0.123这个地址要访问internet，它的数据包就要通过一个网关或者路由器，而网关或者路由器拥有一个能访问internet的ip地址，这样的网关和路由器就要在收发数据包时，对数据包的IP协议层数据进行更改（即  NAT），以使私有网段的主机能够顺利访问internet。此技术解决了IP地址稀缺的问题。同样的私有IP可以网关NAT  上网。     VMWare的NAT上网也是同样的道理，它在主机和虚拟机之间用软件伪造出一块网卡，这块网卡和虚拟机的ip处于一个地址段。同时，在这块网卡和主机的网络接口之间进行NAT。虚拟机发出的每一块数据包都会经过虚拟网卡，然后NAT，然后由主机的接口发出。   虚拟网卡和虚拟机处于一个地址段，虚拟机和主机不同一个地址段，主机相当于虚拟机的网关，所以虚拟机能ping到主机的IP，但是主机ping不到虚拟机的IP。   2、联网方式：   方法1、动态IP地址。   主机是静态IP或动态IP，都无所谓，将虚拟机设置成使用DHCP方式上网,Windows下选择“自动获取IP“，linux下开启DHCP服务即可。（这种方法最简单，不用过多的设置，但要在VMware中进行“编辑→虚拟网络设置”，将NAT和DHCP都开启了。一般NAT默认开启，DHCP默认关闭）   方法2、静态IP地址。   如果不想使用DHCP，也可以手动设置：　   IP设置与vmnet1同网段,网关设置成vmnet8的网关（在“虚拟网络设置”里的Net选项卡里能找到Gateway）通常是xxx.xxx.xxx.2。  子网掩码设置与VMnet8相同（设置好IP地址后，子网掩码自动生成）  DNS设置与主机相同。   例如：主机IP是10.70.54.31,设置虚拟机IP为10.70.54.22。Netmask,Gateway,DNS都与主机相同即可实现  虚拟机  ---主机  虚拟机<---->互联网  通信。     提示：使用NAT技术，主机能上网，虚拟机就可以访问Internet，但是主机不能访问虚拟机。 

\`````````````````````````````````````````````````````````````````````````````````````````````````````````````````````

  三、Host-Only——[私有网络](https://cloud.tencent.com/product/vpc?from_column=20065&from=20065)共享主机：默认使用VMnet1   1、原理：   提供的是主机和虚拟机之间的网络互访。只想让虚拟机和主机之间有数据交换，而不想让虚拟机访问Internet，就要采用这个设置了。   Host-only的条件下，VMWare在真正的Windows系统中，建立一块软网卡。这块网卡可以在网络连接中看到，一般是VMNET1，这块网卡的作用就是使Windows看到虚拟机的IP。   2、联网方法：   方法1、动态IP地址。  像上面那样开启DHCP后，虚拟机直接自动获取IP地址和DNS。就可以和主机相连了。当然，还要进行一些局域网共享的操作，这里不再赘述。   方法2、静态IP地址。     也可以手动设置，将虚拟机IP设置与VMnet1同网段,网关设置成VMnet1的网关相同,其余设置与VMnet1相同,DNS设置与主机相同。   例如：VMnet1  IP:172.16.249.1     Gateway  :172.16.249.2   那么虚拟机  IP:172.16.249.100     Gateway:  172.16.249.2   这样、    虚拟机<--->主机        可以通信      但是、     虚拟机<--->互联网    无法通信   提示：Host-only技术只用于主机和虚拟机互访，于访问internet无关。