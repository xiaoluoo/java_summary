# Centos 7 笔记

## 一、环境安装

#### 简介

##### VMware

   VMware是一款虚拟机软件就是通过软件模拟的具有完整硬件系统功能的、运行在一个完全隔离环境中的完整计算机系统。

  与物理机一样，虚拟机是运行操作系统和应用程序的软件计算机。虚拟机包含一组规范和配置文件，并由主机的物理资源提供支持。每个虚拟机都具有一些虚拟设备，这些设备可提供与物理硬件相同的功能，但是可移植性更强、更安全且更易于管理。

官网：https://www.vmware.com/cn/products/workstation-pro/workstation-pro-evaluation.html

##### CentOS

  CentOS是免费的、开源的、可以重新分发的开源操作系统。全名为“社区企业操作系统（Community Enterprise Operating System）”，提供长期免费升级和更新服务，自由使用。国内最大的服务器操作系统，现在基本所有的互联网公司后台服务器都采用CentOS

官网：[Download![img](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/icon-default.png)https://www.centos.org/download/](https://www.centos.org/download/)

------

#### 安装步骤

##### 一、安装前的准备

1.VMware的安装本文不再介绍，正常安装即可

2.下载CentOS 7 的镜像文件

##### 二、下载镜像文件

![](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/qdqwd2813129327193.png)

![](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/dsadsadiohsadoh32-16337404812941.png)

##### 三、开始安装

1、创建新的虚拟机
![](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/1dd289313893461fa6e462929797ab2c.png)
2、选择自定义
![](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/112796089c4b460699fa2aa603e41460.png)
3、硬盘兼容性-- **默认**
![](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/6a427cbdc7954f9990f269f04960e326-16337405882682.png)
4、稍后安装操作系统（需要在虚拟机安装完成之后，删除不需要的硬件，所以稍后安装操作系统)
![](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/cd046a15d55740f09467df5a02d30aac.png)
5、选择客户端操作系统：

1. 客户机操作系统–Linux
2. 版本–centos 64位

（注意：版本一定要对应镜像文件版本，其中centos是32位，centos 64位则就是64位，windows系统应安装64位版本）
![](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/26bd85e0ad19444bab04358e6a4000b4.png)
6、**命名虚拟机**（简略表示出该虚拟机的类型、版本。例如：centos7 ）
![](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/b63f8d7c4f764c83ad099ab1894db16e.png)
7、处理器配置（CPU）–总处理器核心数一般为 4![](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/62c3c4347e6a40fc8eba26db69b61d07.png)

虚拟机总核心数不能超过主机核心数。若超出则会警告提醒。
![90e6a28e55dc402dae3be53775615c7e](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/90e6a28e55dc402dae3be53775615c7e.png)

8、此虚拟机内存 => **一般2G** 

![](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/829c4c6f5a6e42518b1f22318d701d0f.png)



9、网络类型–桥接网络（可以使虚拟机与主机使用同一网络）
![](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/b61f0d1ee3e743199668b267fda6672b.png)
注释：

- VMnet1网口对应的是仅主机模式
- VMnet8网口对应的是NAT模式
- VMnet0网口对应的是桥接模式

查看以上对应是在VMware workstation中的编辑-虚拟网络编辑器

![](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/a353f4983ef34044b4059d770519f709.png)

10、选择I/O控制器类型（相对于硬盘）-- **默认**
从硬盘到内存是I（input），从内存在硬盘是O（output）
![](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/0a9fffcd16cf4a99927d71b115cfad23.png)
11、选择磁盘类型-- **默认** （硬盘接口，家庭个人常用SATA类型，服务器常用SCSI类型）
![](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/8ddcce346c544c1b980764ee91447c63.png)
12、选择磁盘–创建新的虚拟磁盘（其他两个不常用）
![](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/1b9717fdc8ba4d9592c2c87d1d88a757.png)
13、指定磁盘容量–100G（是假的虚拟的不占主机内存）
![](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/425a1d11afdd421f930f633d8ebc2c19.png)
14、指定磁盘文件（.vmdk）文件
![](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/87046a2ae51e4864b59464d619764c4b.png)
15、完成
![](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/647bb97956084a9994b579c09d85bd6c.png)
**删除不需要的硬件** – 编辑虚拟机设置–删-USB控制器、声卡、打印机（可以使虚拟器启动的快一点）
![](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/321d4e6ae2934eca97dc9d2972c4b650.png)
也可以手动添加硬件，比如，一个网口不够，再添加一个。**（网络连接仍然选择桥接模式)**
![](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/23ede02d93084fe486016fd84a3f7369.png)
此时虚拟机中的硬件已经搭建完成

16、继续添加映像文件，选择设备中的CD/DVD（IDE），在连接处选择–使用ISO映像文件–确定
![](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/78644e458c4245fcad43aa125a0451ff.png)

17、开启虚拟机，选择第一项 Install CentOS 7，等待一段时间；

![](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/95478d83f8c949b5a0e15d9f6f711f62.png)

18、WELCOME TO CENTOS 7.设置语言–推荐使用English–点击Continue

![](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/d3683405b4f648b0a115aafb350c4593.png)

19、INSTALLATION SUMMARY 安装总览（这里可以完成centos 7 版本Linux的全部设置）

1. 首先，设置时区–DATE & TIME，找到Asia–Shanghai并点击–Done
   ![](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/51364f8948064c359653ae74e95473b1.png)
2. KEYBOARD 键盘就默认是English（US）
   ![](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/605a9879f9844a44bd739548576386f1.png)
3. LANGUAGE SUPPORT语言支持
   ![](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/701bf432071649958748040cc0ee2a5d.png)
   可以是默认的English 也可以自行添加Chinese简体中文的支持
4. INSTALLATION SOURCE 安装资源，默认选择–Local media 本地媒体文件
5. SOFTWARE SELECTION软件安装选择，字符界面安装–Minimal install 或者 Basic Web Server
   ![](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/ef04f5b886e344208ff0dda36c445112.png)
   **图形界面安装–Server with GUI 或者 GNOME Desktop**
   字符界面与图形界面安装过程相同，只在这一步有区分。点击–Done进入下一步

20、INSTALLATION DESTINATION 安装位置—即进行系统分区，选中我们在创建虚拟机时候的100G虚拟硬盘
![](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/67cec099b8be497c8be19b6891324afe.png)

21、这是我们已完成所有设置，-- Begin Installation
![](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/a2503f20b9ef451daa05871183eb500a.png)
22、这时需要设置管理员Root Password（务必记住密码！）
![](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/6b1354c37da64a90aa8e6793f7141d3b.png)
接下来可以创建用户（此处可以不进行创建，安装完成后进入root也可以重新创建）
![](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/8b2f11e9d3144ffb92af0bc73991d9ef.png)
23、等待一段时间，centos 7安装完成 – 点击reboot重启使用
![](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/049eefca4b2e4d7291f480bb56e3c3ef.png)
安装完成后如图所示：

![](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/9ed31b60fe5f41b59bd75162faf82b76.png)

##### **四、Centos7网络设置**



###### 1、以系统管理员打开VMWare

![img](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/1346858-20210828220640411-1638143989-163270706427928.png)

 

 

###### 2、选择虚拟网络编辑器菜单

![img](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/1346858-20210828220656139-932999627-163270706147427.png)

 

 

###### 3、选择VMnet8这一行

![img](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/1346858-20210828221055935-751649340-163270705868626.png)

 

 

###### 4、还原VMnet8的默认设置

![img](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/1346858-20210828221043544-1092016821-163270704264925.png)

 

 

###### 5、修改VMnet8的参数

![img](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/1346858-20210828221019608-1050958148-163270704008324.png)

 

 

**虚拟机子网IP地址段和子网掩码由您自己来定，如果你不熟练，就按上图中的内容来设置也没有问题。**

###### 6、NAT设置

![img](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/1346858-20210828220949109-29323353-163270703788623.png)

 

 ![img](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/1346858-20210828221000625-194874741-163270703575622.png)

 

 

 

###### 7、保存设置

![img](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/1346858-20210828220930748-1453195985-163270703416421.png)

 

 

###### 8、确认虚拟机为NAT模式

![img](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/1346858-20210828220911716-260754383-163270703231520.png)

 

 

###### 9、启动虚拟机CentOS7

###### 10、设置CentOS7的不静态IP地址

修改虚拟机网卡配置文件，如/etc/sysconfig/network-scripts/ifcfg-ens33，注意，文件名不一定是ifcfg-ens33，根据您的实际情况决定。

1）修改BOOTPROTO参数，把地址协议改为静态IP方式。

```cpp
BOOTPROTO=static  # dhcp-动态分配，static-静态分配（重要）。
```

2）修改ONBOOT参数，把开机启动选项ONBOOT设置为yes。

```cpp
ONBOOT=yes  # 是否开机引导。
```

3）设置DSN服务器的IP，添加以下内容。

```cpp
DNS1=114.114.114.114  # 第1个DSN服务器的IP地址。
DNS2=1.2.4.8  # 第2个DSN服务器的IP地址。
```

4）设置CentOS7的IP地址、子网掩码和网关参数，添加以下内容。

```cpp
IPADDR=192.168.226.128  # IP地址（重要）。
NETMARSK=255.255.255.0  # 子网掩码（重要）。
GATEWAY=192.168.226.2   # 网关（重要）。
```

###### 11、重启CentOS7的网络服务

```cpp
systemctl restart network
```

###### 12、测试效果

ping一下百度。

![img](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/1346858-20210828220840068-2104581774-163270702933619.png)

ok。

###### 13、注意事项

如果您对网络知识不熟悉，或对虚拟机不熟悉，建议按本文章依葫芦画瓢，照抄参数。

 

二、动态IP上网（所有操作不涉及到IP地址，单纯能连外网）

1、以系统管理员打开VMWare

2、选择虚拟网络编辑器菜单

3、选择VMnet8这一行，勾选三处

*![img](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/1346858-20210828221541766-1435435146-163270702588718.png)*

 

在VMnet8中设置子网号192.168.xx.0,子网掩码为255.255.255.0，然后点开DHCP配置，按照默认的即可

![img](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/1346858-20210828222608262-1675109985-163270702269117.png)

 

 注意一定要在下面“使用本地DHCP服务器将IP地址分配给虚拟机”打钩，否则就是静态NAT了。

4、编辑网卡

输入cd /etc/sysconfig/network-scripts ,然后用打开其中的ifcfg-ens33(我是这个，有些人是32，自己打开这个文件夹ls一下)

执行：vim ifcfg-ens33

然后把其中ONBOOT改为yes，再Esc  :wq退出即可（如果不用root来修改这个文件，保存的时候会出现问题![img](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/1346858-20210828223624526-727798003-163270701856016.png)



5、虚拟机设置，选择网络适配器为NAT(在虚拟机关闭的时候可以在虚拟机设置中打开)

![img](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/1346858-20210828222254631-1521578394-163270701584915.png)

 

 

6、重启网卡生效

*sudo systemctl restart network #重启网卡*

*sudo systemctl enable network #开机启动网卡*

##### 五、关闭防火墙的命令!

###### 1:查看防火状态

```java
systemctl status firewalld

service  iptables status
```

###### 2:暂时关闭防火墙

```java
systemctl stop firewalld

service  iptables stop
```

###### 3:永久关闭防火墙

```java
systemctl disable firewalld

chkconfig iptables off
```

###### 4:重启防火墙

```java
systemctl enable firewalld

service iptables restart  
```

###### 5:永久关闭后重启

```java
chkconfig iptables on
```

#### 问题

##### 		一、无图形界面

​						（在安装CentOS7时，如果选择 “最小化” 安装那么系统就只有命令行界面，但是没有图形化界面）
​							![image-20210926100317797](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/image-20210926100317797.png)

###### 解决措施：

一、先装X windows，-y表示参数同意所有软件安装操，当出现 Complete！说明这里安装成功了。

```
 yum groupinstall "X Window System" -y
```

二、yum grouplist 检查一下我们已经安装的软件以及可以安装的软件，下面安装的名字要和下面的对应起来，否则会出现No packages in any requested group available to install or update 的错误。

![img](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/338023-20210826113925504-564694671.png)

 

 

安装GNOME桌面环境，提示complete!，说明成功。

![img](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/338023-20210826113958410-1351466191.png)

```
 yum groupinstall "GNOME Desktop" "Graphical Administration Tools" -y
```

 **安装报错 transaction check error**

file /boot/efi/EFI/centos from install of fwupdate-efi-12-5.el7.centos.x86_64 conflicts with file from package grub2-common-1:2.02-0.65.el7.centos.2.noarch

用  只升级所有包，不升级软件和系统内核。

```
yum upgrade -y
```

再进行安装即可

三、通过命令 startx 进入图形界面，第一次进入会比较慢，耐心等待就可以了。

四、更新系统的默认运行级别

经过上面的操作，系统启动默认还是命令行页面的，需要我们使用**Ctrl+Alt+F2**进行切换。如果想要使系统启动即为图形化窗口，需要执行下面的命令

```
systemctl set-default graphical.target  #设置成图形模式
或者
ln -sf /lib/systemd/system/runlevel5.target /etc/systemd/system/default.target #默认运行级别5
```

如果要换回默认开机命令模式使用 systemctl set-default multi-user.target #设置成命令模式

五、重启

## 二、软件安装

### 1、node.js

#### 		1)安装步骤：

##### 		centos 7 yum

```
yum install -y epel-release  
/usr/bin/yum install -y nodejs
```

##### 		centos 6安装

- 由于yum源版本过低，cnpm安装失败，使用nvm管理node包的时候

```
yum remove nodejs -y  
curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.29.0/install.sh | bash  
```

- 安装成功后:一定要重新启动shell

```
command -v nvm  
```

- 查看nvm可安装版本

```
nvm ls-remote  
```

- 安装nodejs

```
nvm install v6.12.3  
```

##### 		国内安装源

- cnpm

```
/usr/bin/npm install -g cnpm --registry=https://registry.npm.taobao.org
```

- 配置文件 ~/.npmrc 文件中写入源地址

```
registry =https://registry.npm.taobao.org  
```

#### 		2）问题：

##### 				nvm command not found

​						nvm是node的包版本管理工具，github地址如下：[nvm](https://github.com/creationix/nvm)

​       **安装命令**

```bash
curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.8/install.sh | bash
1
nvm //检查nvm是否安装成功
-bash: nvm: command not found  //boom，失败了
12
```

​		解决nvm command not found问题

​		进入.nvm文件夹，新建.bash_profile：

```bash
touch .bash_profile //新建文件
open .bash_profile //打开文件
12
```

​		在里面copy如下内容：

```bash
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh" # This loads nvm
12
```

​		关闭文件，然后执行这个文件：

```bash
source .bash_profile
1
```

​		执行完毕，我们再看看是否安装成功：

```bash
nvm --version
1
```

​		输出：

```bash
0.33.8
1
```

​		安装成功。

​		卸载：

```bash
$ nvm use system
$ npm uninstall -g a_module
12
```



# Linux 笔记



![linux](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/linux.jpg)

Linux 是一种自由和开放源码的类 UNIX 操作系统。

Linux 英文解释为 **Linux is not Unix**。

Linux 是在 1991 由林纳斯·托瓦兹在赫尔辛基大学上学时创立的，主要受到 Minix 和 Unix 思想的启发。

本教程，我们将为大家介绍如何使用 Linux。

Linux 其实很容易学，相信你们能很快学会。



## 一、常用命令



### 1、yum 



#### yum简介

Docker 笔记yum（ Yellow dog Updater, Modified）是一个在 Fedora 和 RedHat 以及 SUSE 中的 Shell 前端软件包管理器。

基于 RPM 包管理，能够从指定的服务器自动下载 RPM 包并且安装，可以自动处理依赖性关系，并且一次安装所有依赖的软件包，无须繁琐地一次次下载、安装。

yum 提供了查找、安装、删除某一个、一组甚至全部软件包的命令，而且命令简洁而又好记。

#### yum 语法

```
yum [options] [command] [package ...]
```

- **options：**可选，选项包括-h（帮助），-y（当安装过程提示选择全部为 "yes"），-q（不显示安装的过程）等等。
- **command：**要进行的操作。
- **package：**安装的包名。

------

#### yum常用命令

列出所有可更新的软件清单命令：

```shell
yum check-update
```

 更新所有软件命令：

```shell
yum update
```

 仅安装指定的软件命令：

```shell
yum install <package_name>
```

仅更新指定的软件命令：

```shell
yum update <package_name>
```

列出所有可安裝的软件清单命令：

```shell
yum list
```

 删除软件包命令：

```shell
yum remove <package_name>
```

 查找软件包命令：

```shel
yum search <keyword>
```

清除缓存命令:

```shell
yum clean packages: 清除缓存目录下的软件包

yum clean headers: 清除缓存目录下的 headers

yum clean oldheaders: 清除缓存目录下旧的 headers

yum clean, yum clean all (= yum clean packages; yum clean oldheaders):清除缓存目录下的软件包及旧的 headers
```

### 2、文件与目录管理

我们知道Linux的目录结构为树状结构，最顶级的目录为根目录 /。

其他目录通过挂载可以将它们添加到树中，通过解除挂载可以移除它们。

在开始本教程前我们需要先知道什么是绝对路径与相对路径。

- **绝对路径：**
  路径的写法，由根目录 **/** 写起，例如： /usr/share/doc 这个目录。

- 

  **相对路径：**
  路径的写法，不是由 **/** 写起，例如由 /usr/share/doc 要到 /usr/share/man 底下时，可以写成： **cd ../man** 这就是相对路径的写法。

------

#### 处理目录的常用命令

接下来我们就来看几个常见的处理目录的命令吧：

- ls（英文全拼：list files）: 列出目录及文件名
- cd（英文全拼：change directory）：切换目录
- pwd（英文全拼：print work directory）：显示目前的目录
- mkdir（英文全拼：make directory）：创建一个新的目录
- rmdir（英文全拼：remove directory）：删除一个空的目录
- cp（英文全拼：copy file）: 复制文件或目录
- rm（英文全拼：remove）: 删除文件或目录
- mv（英文全拼：move file）: 移动文件与目录，或修改文件与目录的名称

你可以使用 *man [命令]* 来查看各个命令的使用文档，如 ：man cp。

##### ls (列出目录)

在Linux系统当中， ls 命令可能是最常被运行的。

语法：

```
[root@www ~]# ls [-aAdfFhilnrRSt] 目录名称
[root@www ~]# ls [--color={never,auto,always}] 目录名称
[root@www ~]# ls [--full-time] 目录名称
```

选项与参数：

- -a ：全部的文件，连同隐藏文件( 开头为 . 的文件) 一起列出来(常用)
- -d ：仅列出目录本身，而不是列出目录内的文件数据(常用)
- -l ：长数据串列出，包含文件的属性与权限等等数据；(常用)

将家目录下的所有文件列出来(含属性与隐藏档)

```
[root@www ~]# ls -al ~
```

##### cd (切换目录)

cd是Change Directory的缩写，这是用来变换工作目录的命令。

语法：

```
 cd [相对路径或绝对路径]
#使用 mkdir 命令创建 runoob 目录
[root@www ~]# mkdir runoob

#使用绝对路径切换到 runoob 目录
[root@www ~]# cd /root/runoob/

#使用相对路径切换到 runoob 目录
[root@www ~]# cd ./runoob/

# 表示回到自己的家目录，亦即是 /root 这个目录
[root@www runoob]# cd ~

# 表示去到目前的上一级目录，亦即是 /root 的上一级目录的意思；
[root@www ~]# cd ..
```

接下来大家多操作几次应该就可以很好的理解 cd 命令的。

##### pwd (显示目前所在的目录)

pwd 是 **Print Working Directory** 的缩写，也就是显示目前所在目录的命令。

```
[root@www ~]# pwd [-P]
```

选项与参数：

- **-P** ：显示出确实的路径，而非使用连结 (link) 路径。

实例：单纯显示出目前的工作目录：

```
[root@www ~]# pwd
/root   <== 显示出目录啦～
```

实例显示出实际的工作目录，而非连结档本身的目录名而已。

```
[root@www ~]# cd /var/mail   <==注意，/var/mail是一个连结档
[root@www mail]# pwd
/var/mail         <==列出目前的工作目录
[root@www mail]# pwd -P
/var/spool/mail   <==怎么回事？有没有加 -P 差很多～
[root@www mail]# ls -ld /var/mail
lrwxrwxrwx 1 root root 10 Sep  4 17:54 /var/mail -> spool/mail
# 看到这里应该知道为啥了吧？因为 /var/mail 是连结档，连结到 /var/spool/mail 
# 所以，加上 pwd -P 的选项后，会不以连结档的数据显示，而是显示正确的完整路径啊！
```

##### mkdir (创建新目录)

如果想要创建新的目录的话，那么就使用mkdir (make directory)吧。

语法：

```
mkdir [-mp] 目录名称
```

选项与参数：

- -m ：配置文件的权限喔！直接配置，不需要看默认权限 (umask) 的脸色～
- -p ：帮助你直接将所需要的目录(包含上一级目录)递归创建起来！

实例：请到/tmp底下尝试创建数个新目录看看：

```
[root@www ~]# cd /tmp
[root@www tmp]# mkdir test    <==创建一名为 test 的新目录
[root@www tmp]# mkdir test1/test2/test3/test4
mkdir: cannot create directory `test1/test2/test3/test4': 
No such file or directory       <== 没办法直接创建此目录啊！
[root@www tmp]# mkdir -p test1/test2/test3/test4
```

加了这个 -p 的选项，可以自行帮你创建多层目录！

实例：创建权限为 **rwx--x--x** 的目录。

```
[root@www tmp]# mkdir -m 711 test2
[root@www tmp]# ls -l
drwxr-xr-x  3 root  root 4096 Jul 18 12:50 test
drwxr-xr-x  3 root  root 4096 Jul 18 12:53 test1
drwx--x--x  2 root  root 4096 Jul 18 12:54 test2
```

上面的权限部分，如果没有加上 -m 来强制配置属性，系统会使用默认属性。

如果我们使用 -m ，如上例我们给予 -m 711 来给予新的目录 drwx--x--x 的权限。

##### rmdir (删除空的目录)

语法：

```
 rmdir [-p] 目录名称
```

选项与参数：

- **-p ：**从该目录起，一次删除多级空目录

删除 runoob 目录

```
[root@www tmp]# rmdir runoob/
```

将 mkdir 实例中创建的目录(/tmp 底下)删除掉！

```
[root@www tmp]# ls -l   <==看看有多少目录存在？
drwxr-xr-x  3 root  root 4096 Jul 18 12:50 test
drwxr-xr-x  3 root  root 4096 Jul 18 12:53 test1
drwx--x--x  2 root  root 4096 Jul 18 12:54 test2
[root@www tmp]# rmdir test   <==可直接删除掉，没问题
[root@www tmp]# rmdir test1  <==因为尚有内容，所以无法删除！
rmdir: `test1': Directory not empty
[root@www tmp]# rmdir -p test1/test2/test3/test4
[root@www tmp]# ls -l        <==您看看，底下的输出中test与test1不见了！
drwx--x--x  2 root  root 4096 Jul 18 12:54 test2
```

利用 -p 这个选项，立刻就可以将 test1/test2/test3/test4 一次删除。

不过要注意的是，这个 rmdir 仅能删除空的目录，你可以使用 rm 命令来删除非空目录。

##### cp (复制文件或目录)

cp 即拷贝文件和目录。

语法:

```
[root@www ~]# cp [-adfilprsu] 来源档(source) 目标档(destination)
[root@www ~]# cp [options] source1 source2 source3 .... directory
```

选项与参数：

- **-a：**相当於 -pdr 的意思，至於 pdr 请参考下列说明；(常用)
- **-d：**若来源档为连结档的属性(link file)，则复制连结档属性而非文件本身；
- **-f：**为强制(force)的意思，若目标文件已经存在且无法开启，则移除后再尝试一次；
- **-i：**若目标档(destination)已经存在时，在覆盖时会先询问动作的进行(常用)
- **-l：**进行硬式连结(hard link)的连结档创建，而非复制文件本身；
- **-p：**连同文件的属性一起复制过去，而非使用默认属性(备份常用)；
- **-r：**递归持续复制，用於目录的复制行为；(常用)
- **-s：**复制成为符号连结档 (symbolic link)，亦即『捷径』文件；
- **-u：**若 destination 比 source 旧才升级 destination ！

用 root 身份，将 root 目录下的 .bashrc 复制到 /tmp 下，并命名为 bashrc

```
[root@www ~]# cp ~/.bashrc /tmp/bashrc
[root@www ~]# cp -i ~/.bashrc /tmp/bashrc
cp: overwrite `/tmp/bashrc'? n  <==n不覆盖，y为覆盖
```

##### rm (移除文件或目录)

语法：

```
 rm [-fir] 文件或目录
```

选项与参数：

- -f ：就是 force 的意思，忽略不存在的文件，不会出现警告信息；
- -i ：互动模式，在删除前会询问使用者是否动作
- -r ：递归删除啊！最常用在目录的删除了！这是非常危险的选项！！！
- 

将刚刚在 cp 的实例中创建的 bashrc 删除掉！

```
[root@www tmp]# rm -i bashrc
rm: remove regular file `bashrc'? y
rm -rf bashrc/ 删除目录
```

如果加上 -i 的选项就会主动询问喔，避免你删除到错误的档名！

##### mv (移动文件与目录，或修改名称)

语法：

```
[root@www ~]# mv [-fiu] source destination
[root@www ~]# mv [options] source1 source2 source3 .... directory
```

选项与参数：

- -f ：force 强制的意思，如果目标文件已经存在，不会询问而直接覆盖；
- -i ：若目标文件 (destination) 已经存在时，就会询问是否覆盖！
- -u ：若目标文件已经存在，且 source 比较新，才会升级 (update)

复制一文件，创建一目录，将文件移动到目录中

```
[root@www ~]# cd /tmp
[root@www tmp]# cp ~/.bashrc bashrc
[root@www tmp]# mkdir mvtest
[root@www tmp]# mv bashrc mvtest
```

将某个文件移动到某个目录去，就是这样做！

将刚刚的目录名称更名为 mvtest2

```
[root@www tmp]# mv mvtest mvtest2
```

------

#### Linux 文件内容查看

Linux系统中使用以下命令来查看文件的内容：

- cat 由第一行开始显示文件内容
- tac 从最后一行开始显示，可以看出 tac 是 cat 的倒着写！
- nl  显示的时候，顺道输出行号！
- more 一页一页的显示文件内容
- less 与 more 类似，但是比 more 更好的是，他可以往前翻页！
- head 只看头几行
- tail 只看尾巴几行

你可以使用 *man [命令]*来查看各个命令的使用文档，如 ：man cp。

##### cat

由第一行开始显示文件内容

语法：

```
cat [-AbEnTv]
```

选项与参数：

- -A ：相当於 -vET 的整合选项，可列出一些特殊字符而不是空白而已；
- -b ：列出行号，仅针对非空白行做行号显示，空白行不标行号！
- -E ：将结尾的断行字节 $ 显示出来；
- -n ：列印出行号，连同空白行也会有行号，与 -b 的选项不同；
- -T ：将 [tab] 按键以 ^I 显示出来；
- -v ：列出一些看不出来的特殊字符

检看 /etc/issue 这个文件的内容：

```
[root@www ~]# cat /etc/issue
CentOS release 6.4 (Final)
Kernel \r on an \m
```

##### tac

tac与cat命令刚好相反，文件内容从最后一行开始显示，可以看出 tac 是 cat 的倒着写！如：

```
[root@www ~]# tac /etc/issue

Kernel \r on an \m
CentOS release 6.4 (Final)
```

##### nl

显示行号

语法：

```
nl [-bnw] 文件
```

选项与参数：

- -b ：指定行号指定的方式，主要有两种：
  -b a ：表示不论是否为空行，也同样列出行号(类似 cat -n)；
  -b t ：如果有空行，空的那一行不要列出行号(默认值)；
- -n ：列出行号表示的方法，主要有三种：
  -n ln ：行号在荧幕的最左方显示；
  -n rn ：行号在自己栏位的最右方显示，且不加 0 ；
  -n rz ：行号在自己栏位的最右方显示，且加 0 ；
- -w ：行号栏位的占用的位数。

实例一：用 nl 列出 /etc/issue 的内容

```
[root@www ~]# nl /etc/issue
     1  CentOS release 6.4 (Final)
     2  Kernel \r on an \m
```

##### more

一页一页翻动

```
[root@www ~]# more /etc/man_db.config 
#
# Generated automatically from man.conf.in by the
# configure script.
#
# man.conf from man-1.6d
....(中间省略)....
--More--(28%)  <== 重点在这一行喔！你的光标也会在这里等待你的命令
```

在 more 这个程序的运行过程中，你有几个按键可以按的：

- 空白键 (space)：代表向下翻一页；
- Enter     ：代表向下翻『一行』；
- /字串     ：代表在这个显示的内容当中，向下搜寻『字串』这个关键字；
- :f      ：立刻显示出档名以及目前显示的行数；
- q       ：代表立刻离开 more ，不再显示该文件内容。
- b 或 [ctrl]-b ：代表往回翻页，不过这动作只对文件有用，对管线无用。

##### less

一页一页翻动，以下实例输出/etc/man.config文件的内容：

```
[root@www ~]# less /etc/man.config
#
# Generated automatically from man.conf.in by the
# configure script.
#
# man.conf from man-1.6d
....(中间省略)....
:   <== 这里可以等待你输入命令！
```

less运行时可以输入的命令有：

- 空白键  ：向下翻动一页；
- [pagedown]：向下翻动一页；
- [pageup] ：向上翻动一页；
- /字串   ：向下搜寻『字串』的功能；
- ?字串   ：向上搜寻『字串』的功能；
- n     ：重复前一个搜寻 (与 / 或 ? 有关！)
- N     ：反向的重复前一个搜寻 (与 / 或 ? 有关！)
- q     ：离开 less 这个程序；

##### head

取出文件前面几行

语法：

```
head [-n number] 文件 
```

选项与参数：

- -n ：后面接数字，代表显示几行的意思

```
[root@www ~]# head /etc/man.config
```

默认的情况中，显示前面 10 行！若要显示前 20 行，就得要这样：

```
[root@www ~]# head -n 20 /etc/man.config
```

##### tail

取出文件后面几行

语法：

```
tail [-n number] 文件 
```

选项与参数：

- -n ：后面接数字，代表显示几行的意思
- -f ：表示持续侦测后面所接的档名，要等到按下[ctrl]-c才会结束tail的侦测

```
[root@www ~]# tail /etc/man.config
# 默认的情况中，显示最后的十行！若要显示最后的 20 行，就得要这样：
[root@www ~]# tail -n 20 /etc/man.config
```





### 3、ps



Linux ps （英文全拼：process status）命令用于显示当前进程的状态，类似于 windows 的任务管理器。

#### 语法

```
ps [options] [--help]
```

**参数**：

- ps 的参数非常多, 在此仅列出几个常用的参数并大略介绍含义

- -A 列出所有的进程

- -w 显示加宽可以显示较多的资讯

- -au 显示较详细的资讯

- -aux 显示所有包含其他使用者的行程

- au(x) 输出格式 :

  ```
  USER PID %CPU %MEM VSZ RSS TTY STAT START TIME COMMAND
  ```

  - USER: 行程拥有者
  - PID: pid
  - %CPU: 占用的 CPU 使用率
  - %MEM: 占用的记忆体使用率
  - VSZ: 占用的虚拟记忆体大小
  - RSS: 占用的记忆体大小
  - TTY: 终端的次要装置号码 (minor device number of tty)
  - STAT: 该行程的状态:
    - D: 无法中断的休眠状态 (通常 IO 的进程)
    - R: 正在执行中
    - S: 静止状态
    - T: 暂停执行
    - Z: 不存在但暂时无法消除
    - W: 没有足够的记忆体分页可分配
    - <: 高优先序的行程
    - N: 低优先序的行程
    - L: 有记忆体分页分配并锁在记忆体内 (实时系统或捱A I/O)
  - START: 行程开始时间
  - TIME: 执行的时间
  - COMMAND:所执行的指令

#### 实例

查找指定进程格式：

```
ps -ef | grep 进程关键字
```





### 4、 文件基本属性



Linux 系统是一种典型的多用户系统，不同的用户处于不同的地位，拥有不同的权限。

为了保护系统的安全性，Linux 系统对不同的用户访问同一文件（包括目录文件）的权限做了不同的规定。

在 Linux 中我们通常使用以下两个命令来修改文件或目录的所属用户与权限：

- chown (change ownerp) ： 修改所属用户与组。
- chmod (change mode) ： 修改用户的权限。

下图中通过 chown 来授权用户，通过 chmod 为用户设置可以开门的权限。

![img](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/1_151733904241.png)

在 Linux 中我们可以使用 **ll** 或者 **ls –l** 命令来显示一个文件的属性以及文件所属的用户和组，如：

```
[root@www /]# ls -l
total 64
dr-xr-xr-x   2 root root 4096 Dec 14  2012 bin
dr-xr-xr-x   4 root root 4096 Apr 19  2012 boot
……
```

实例中，**bin** 文件的第一个属性用 **d** 表示。**d** 在 Linux 中代表该文件是一个目录文件。

在 Linux 中第一个字符代表这个文件是目录、文件或链接文件等等。

- 当为 **d** 则是目录
- 当为 **-** 则是文件；
- 若是 **l** 则表示为链接文档(link file)；
- 若是 **b** 则表示为装置文件里面的可供储存的接口设备(可随机存取装置)；
- 若是 **c** 则表示为装置文件里面的串行端口设备，例如键盘、鼠标(一次性读取装置)。

接下来的字符中，以三个为一组，且均为 **rwx** 的三个参数的组合。其中， **r** 代表可读(read)、 **w** 代表可写(write)、 **x** 代表可执行(execute)。 要注意的是，这三个权限的位置不会改变，如果没有权限，就会出现减号 **-** 而已。

![img](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/file-llls22.jpg)

每个文件的属性由左边第一部分的 10 个字符来确定（如下图）。

![363003_1227493859FdXT](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/363003_1227493859FdXT.png)

从左至右用 **0-9** 这些数字来表示。

第 **0** 位确定文件类型，第 **1-3** 位确定属主（该文件的所有者）拥有该文件的权限。

第4-6位确定属组（所有者的同组用户）拥有该文件的权限，第7-9位确定其他用户拥有该文件的权限。



其中，第 **1、4、7** 位表示读权限，如果用 **r** 字符表示，则有读权限，如果用 **-** 字符表示，则没有读权限；

第 **2、5、8** 位表示写权限，如果用 **w** 字符表示，则有写权限，如果用 **-** 字符表示没有写权限；第 **3、6、9** 位表示可执行权限，如果用 **x** 字符表示，则有执行权限，如果用 **-** 字符表示，则没有执行权限。



#### 文件属主和属组



```
[root@www /]# ls -l
total 64
drwxr-xr-x 2 root  root  4096 Feb 15 14:46 cron
drwxr-xr-x 3 mysql mysql 4096 Apr 21  2014 mysql
……
```

对于文件来说，它都有一个特定的所有者，也就是对该文件具有所有权的用户。

同时，在Linux系统中，用户是按组分类的，一个用户属于一个或多个组。

文件所有者以外的用户又可以分为文件所有者的同组用户和其他用户。

因此，Linux系统按文件所有者、文件所有者同组用户和其他用户来规定了不同的文件访问权限。

在以上实例中，mysql 文件是一个目录文件，属主和属组都为 mysql，属主有可读、可写、可执行的权限；与属主同组的其他用户有可读和可执行的权限；其他用户也有可读和可执行的权限。

对于 root 用户来说，一般情况下，文件的权限对其不起作用。

------

#### 更改文件属性

##### 1、chgrp：更改文件属组

语法：

```
chgrp [-R] 属组名 文件名
```

参数选项

- -R：递归更改文件属组，就是在更改某个目录文件的属组时，如果加上-R的参数，那么该目录下的所有文件的属组都会更改。

##### 2、chown：更改文件属主，也可以同时更改文件属组

语法：

```
chown [–R] 属主名 文件名
chown [-R] 属主名：属组名 文件名
```

进入 /root 目录（~）将install.log的拥有者改为bin这个账号：

```
[root@www ~] cd ~
[root@www ~]# chown bin install.log
[root@www ~]# ls -l
-rw-r--r--  1 bin  users 68495 Jun 25 08:53 install.log
```

将install.log的拥有者与群组改回为root：

```
[root@www ~]# chown root:root install.log
[root@www ~]# ls -l
-rw-r--r--  1 root root 68495 Jun 25 08:53 install.log
```

##### 3、chmod：更改文件9个属性

Linux文件属性有两种设置方法，一种是数字，一种是符号。

Linux 文件的基本权限就有九个，分别是 **owner/group/others(拥有者/组/其他)** 三种身份各有自己的 **read/write/execute** 权限。

先复习一下刚刚上面提到的数据：文件的权限字符为： **-rwxrwxrwx** ， 这九个权限是三个三个一组的！其中，我们可以使用数字来代表各个权限，各权限的分数对照表如下：

- r:4
- w:2
- x:1

每种身份(owner/group/others)各自的三个权限(r/w/x)分数是需要累加的，例如当权限为： **-rwxrwx---** 分数则是：

- owner = rwx = 4+2+1 = 7
- group = rwx = 4+2+1 = 7
- others= --- = 0+0+0 = 0

所以等一下我们设定权限的变更时，该文件的权限数字就是 **770**。变更权限的指令 chmod 的语法是这样的：

```
 chmod [-R] xyz 文件或目录
```

选项与参数：

- xyz : 就是刚刚提到的数字类型的权限属性，为 rwx 属性数值的相加。
- -R : 进行递归(recursive)的持续变更，亦即连同次目录下的所有文件都会变更

举例来说，如果要将 .bashrc 这个文件所有的权限都设定启用，那么命令如下：

```
[root@www ~]# ls -al .bashrc
-rw-r--r--  1 root root 395 Jul  4 11:45 .bashrc
[root@www ~]# chmod 777 .bashrc
[root@www ~]# ls -al .bashrc
-rwxrwxrwx  1 root root 395 Jul  4 11:45 .bashrc
```

那如果要将权限变成 *-rwxr-xr--* 呢？那么权限的分数就成为 [4+2+1][4+0+1][4+0+0]=754。

##### 符号类型改变文件权限

还有一个改变权限的方法，从之前的介绍中我们可以发现，基本上就九个权限分别是：

- user：用户
- group：组
- others：其他

那么我们就可以使用 **u, g, o** 来代表三种身份的权限。

此外， **a** 则代表 **all**，即全部的身份。读写的权限可以写成 **r, w, x**，也就是可以使用下表的方式来看：



| chmod | u g o a | +(加入) -(除去) =(设定) | r w x | 文件或目录 |
| ----- | ------- | ----------------------- | ----- | ---------- |
|       |         |                         |       |            |

如果我们需要将文件权限设置为 **-rwxr-xr--** ，可以使用 **chmod u=rwx,g=rx,o=r 文件名** 来设定:

```
#  touch test1    // 创建 test1 文件
# ls -al test1    // 查看 test1 默认权限
-rw-r--r-- 1 root root 0 Nov 15 10:32 test1
# chmod u=rwx,g=rx,o=r  test1    // 修改 test1 权限
# ls -al test1
-rwxr-xr-- 1 root root 0 Nov 15 10:32 test1
```

而如果是要将权限去掉而不改变其他已存在的权限呢？例如要拿掉全部人的可执行权限，则：

```
#  chmod  a-x test1
# ls -al test1
-rw-r--r-- 1 root root 0 Nov 15 10:32 test1
```



### 5、用户和用户组管理

Linux系统是一个多用户多任务的分时操作系统，任何一个要使用系统资源的用户，都必须首先向系统管理员申请一个账号，然后以这个账号的身份进入系统。

用户的账号一方面可以帮助系统管理员对使用系统的用户进行跟踪，并控制他们对系统资源的访问；另一方面也可以帮助用户组织文件，并为用户提供安全性保护。

每个用户账号都拥有一个唯一的用户名和各自的口令。

用户在登录时键入正确的用户名和口令后，就能够进入系统和自己的主目录。

实现用户账号的管理，要完成的工作主要有如下几个方面：

- 用户账号的添加、删除与修改。

- 用户口令的管理。

- 用户组的管理。

  



#### 一、Linux系统用户账号的管理

用户账号的管理工作主要涉及到用户账号的添加、修改和删除。

添加用户账号就是在系统中创建一个新账号，然后为新账号分配用户号、用户组、主目录和登录Shell等资源。刚添加的账号是被锁定的，无法使用。

##### 1、添加新的用户账号使用useradd命令，其语法如下：

```
useradd 选项 用户名
```

参数说明：

- 选项:

  - -c comment 指定一段注释性描述。
  - -d 目录 指定用户主目录，如果此目录不存在，则同时使用-m选项，可以创建主目录。
  - -g 用户组 指定用户所属的用户组。
  - -G 用户组，用户组 指定用户所属的附加组。
  - -s Shell文件 指定用户的登录Shell。
  - -u 用户号 指定用户的用户号，如果同时有-o选项，则可以重复使用其他用户的标识号。

- 用户名:

  指定新账号的登录名。

###### 实例1

```
# useradd –d  /home/sam -m sam
```

此命令创建了一个用户sam，其中-d和-m选项用来为登录名sam产生一个主目录 /home/sam（/home为默认的用户主目录所在的父目录）。

###### 实例2

```
# useradd -s /bin/sh -g group –G adm,root gem
```

此命令新建了一个用户gem，该用户的登录Shell是 `/bin/sh`，它属于group用户组，同时又属于adm和root用户组，其中group用户组是其主组。

这里可能新建组：`#groupadd group及groupadd adm`

增加用户账号就是在/etc/passwd文件中为新用户增加一条记录，同时更新其他系统文件如/etc/shadow, /etc/group等。

Linux提供了集成的系统管理工具userconf，它可以用来对用户账号进行统一管理。

##### 2、删除帐号

如果一个用户的账号不再使用，可以从系统中删除。删除用户账号就是要将/etc/passwd等系统文件中的该用户记录删除，必要时还删除用户的主目录。

删除一个已有的用户账号使用`userdel`命令，其格式如下：

```
userdel 选项 用户名
```

常用的选项是 **-r**，它的作用是把用户的主目录一起删除。

例如：

```
# userdel -r sam
```

此命令删除用户sam在系统文件中（主要是/etc/passwd, /etc/shadow, /etc/group等）的记录，同时删除用户的主目录。

##### 3、修改帐号

修改用户账号就是根据实际情况更改用户的有关属性，如用户号、主目录、用户组、登录Shell等。

修改已有用户的信息使用`usermod`命令，其格式如下：

```
usermod 选项 用户名
```

常用的选项包括`-c, -d, -m, -g, -G, -s, -u以及-o等`，这些选项的意义与`useradd`命令中的选项一样，可以为用户指定新的资源值。

另外，有些系统可以使用选项：-l 新用户名

这个选项指定一个新的账号，即将原来的用户名改为新的用户名。

例如：

```
# usermod -s /bin/ksh -d /home/z –g developer sam
```

此命令将用户sam的登录Shell修改为ksh，主目录改为/home/z，用户组改为developer。

##### 4、用户口令的管理

用户管理的一项重要内容是用户口令的管理。用户账号刚创建时没有口令，但是被系统锁定，无法使用，必须为其指定口令后才可以使用，即使是指定空口令。

指定和修改用户口令的Shell命令是`passwd`。超级用户可以为自己和其他用户指定口令，普通用户只能用它修改自己的口令。命令的格式为：

```
passwd 选项 用户名
```

可使用的选项：

- -l 锁定口令，即禁用账号。
- -u 口令解锁。
- -d 使账号无口令。
- -f 强迫用户下次登录时修改口令。

如果默认用户名，则修改当前用户的口令。

例如，假设当前用户是sam，则下面的命令修改该用户自己的口令：

```
$ passwd 
Old password:****** 
New password:******* 
Re-enter new password:*******
```

如果是超级用户，可以用下列形式指定任何用户的口令：

```
# passwd sam 
New password:******* 
Re-enter new password:*******
```

普通用户修改自己的口令时，passwd命令会先询问原口令，验证后再要求用户输入两遍新口令，如果两次输入的口令一致，则将这个口令指定给用户；而超级用户为用户指定口令时，就不需要知道原口令。

为了系统安全起见，用户应该选择比较复杂的口令，例如最好使用8位长的口令，口令中包含有大写、小写字母和数字，并且应该与姓名、生日等不相同。

为用户指定空口令时，执行下列形式的命令：

```
# passwd -d sam
```

此命令将用户 sam 的口令删除，这样用户 sam 下一次登录时，系统就不再允许该用户登录了。

passwd 命令还可以用 -l(lock) 选项锁定某一用户，使其不能登录，例如：

```
# passwd -l sam
```

------

#### 二、Linux系统用户组的管理

每个用户都有一个用户组，系统可以对一个用户组中的所有用户进行集中管理。不同Linux 系统对用户组的规定有所不同，如Linux下的用户属于与它同名的用户组，这个用户组在创建用户时同时创建。

用户组的管理涉及用户组的添加、删除和修改。组的增加、删除和修改实际上就是对/etc/group文件的更新。

##### 1、增加一个新的用户组使用groupadd命令。其格式如下：

```
groupadd 选项 用户组
```

可以使用的选项有：

- -g GID 指定新用户组的组标识号（GID）。
- -o 一般与-g选项同时使用，表示新用户组的GID可以与系统已有用户组的GID相同。

###### 实例1：

```
# groupadd group1
```

此命令向系统中增加了一个新组group1，新组的组标识号是在当前已有的最大组标识号的基础上加1。

###### 实例2：

```
# groupadd -g 101 group2
```

此命令向系统中增加了一个新组group2，同时指定新组的组标识号是101。

##### 2、如果要删除一个已有的用户组，使用groupdel命令，其格式如下：

```
groupdel 用户组
```

###### 例如：

```
# groupdel group1
```

此命令从系统中删除组group1。

##### 3、修改用户组的属性使用groupmod命令。其语法如下：

```
groupmod 选项 用户组
```

常用的选项有：

- -g GID 为用户组指定新的组标识号。
- -o 与-g选项同时使用，用户组的新GID可以与系统已有用户组的GID相同。
- -n新用户组 将用户组的名字改为新名字

###### 实例1：

```
# groupmod -g 102 group2
```

此命令将组group2的组标识号修改为102。

###### 实例2：

```
# groupmod –g 10000 -n group3 group2
```

此命令将组group2的标识号改为10000，组名修改为group3。

##### 4、如果一个用户同时属于多个用户组，那么用户可以在用户组之间切换，以便具有其他用户组的权限。

用户可以在登录后，使用命令newgrp切换到其他用户组，这个命令的参数就是目的用户组。例如：

```
$ newgrp root
```

这条命令将当前用户切换到root用户组，前提条件是root用户组确实是该用户的主组或附加组。类似于用户账号的管理，用户组的管理也可以通过集成的系统管理工具来完成。

------

#### 三、与用户账号有关的系统文件

完成用户管理的工作有许多种方法，但是每一种方法实际上都是对有关的系统文件进行修改。

与用户和用户组相关的信息都存放在一些系统文件中，这些文件包括/etc/passwd, /etc/shadow, /etc/group等。

下面分别介绍这些文件的内容。

##### 1、/etc/passwd文件是用户管理工作涉及的最重要的一个文件。

Linux系统中的每个用户都在/etc/passwd文件中有一个对应的记录行，它记录了这个用户的一些基本属性。

这个文件对所有用户都是可读的。它的内容类似下面的例子：

```
＃ cat /etc/passwd

root:x:0:0:Superuser:/:
daemon:x:1:1:System daemons:/etc:
bin:x:2:2:Owner of system commands:/bin:
sys:x:3:3:Owner of system files:/usr/sys:
adm:x:4:4:System accounting:/usr/adm:
uucp:x:5:5:UUCP administrator:/usr/lib/uucp:
auth:x:7:21:Authentication administrator:/tcb/files/auth:
cron:x:9:16:Cron daemon:/usr/spool/cron:
listen:x:37:4:Network daemon:/usr/net/nls:
lp:x:71:18:Printer administrator:/usr/spool/lp:
sam:x:200:50:Sam san:/home/sam:/bin/sh
```

从上面的例子我们可以看到，/etc/passwd中一行记录对应着一个用户，每行记录又被冒号(:)分隔为7个字段，其格式和具体含义如下：

```
用户名:口令:用户标识号:组标识号:注释性描述:主目录:登录Shell
```

###### 1）"用户名"是代表用户账号的字符串。

通常长度不超过8个字符，并且由大小写字母和/或数字组成。登录名中不能有冒号(:)，因为冒号在这里是分隔符。

为了兼容起见，登录名中最好不要包含点字符(.)，并且不使用连字符(-)和加号(+)打头。

###### 2）“口令”一些系统中，存放着加密后的用户口令字。

虽然这个字段存放的只是用户口令的加密串，不是明文，但是由于/etc/passwd文件对所有用户都可读，所以这仍是一个安全隐患。因此，现在许多Linux 系统（如SVR4）都使用了shadow技术，把真正的加密后的用户口令字存放到/etc/shadow文件中，而在/etc/passwd文件的口令字段中只存放一个特殊的字符，例如“x”或者“*”。

###### 3）“用户标识号”是一个整数，系统内部用它来标识用户。

一般情况下它与用户名是一一对应的。如果几个用户名对应的用户标识号是一样的，系统内部将把它们视为同一个用户，但是它们可以有不同的口令、不同的主目录以及不同的登录Shell等。

通常用户标识号的取值范围是0～65 535。0是超级用户root的标识号，1～99由系统保留，作为管理账号，普通用户的标识号从100开始。在Linux系统中，这个界限是500。

###### 4）“组标识号”字段记录的是用户所属的用户组。

它对应着/etc/group文件中的一条记录。

###### 5)“注释性描述”字段记录着用户的一些个人情况。

例如用户的真实姓名、电话、地址等，这个字段并没有什么实际的用途。在不同的Linux 系统中，这个字段的格式并没有统一。在许多Linux系统中，这个字段存放的是一段任意的注释性描述文字，用做finger命令的输出。

###### 6)“主目录”，也就是用户的起始工作目录。

它是用户在登录到系统之后所处的目录。在大多数系统中，各用户的主目录都被组织在同一个特定的目录下，而用户主目录的名称就是该用户的登录名。各用户对自己的主目录有读、写、执行（搜索）权限，其他用户对此目录的访问权限则根据具体情况设置。

###### 7)用户登录后，要启动一个进程，负责将用户的操作传给内核，这个进程是用户登录到系统后运行的命令解释器或某个特定的程序，即Shell。

Shell是用户与Linux系统之间的接口。Linux的Shell有许多种，每种都有不同的特点。常用的有sh(Bourne Shell), csh(C Shell), ksh(Korn Shell), tcsh(TENEX/TOPS-20 type C Shell), bash(Bourne Again Shell)等。

系统管理员可以根据系统情况和用户习惯为用户指定某个Shell。如果不指定Shell，那么系统使用sh为默认的登录Shell，即这个字段的值为/bin/sh。

用户的登录Shell也可以指定为某个特定的程序（此程序不是一个命令解释器）。

利用这一特点，我们可以限制用户只能运行指定的应用程序，在该应用程序运行结束后，用户就自动退出了系统。有些Linux 系统要求只有那些在系统中登记了的程序才能出现在这个字段中。

###### 8)系统中有一类用户称为伪用户（pseudo users）。

这些用户在/etc/passwd文件中也占有一条记录，但是不能登录，因为它们的登录Shell为空。它们的存在主要是方便系统管理，满足相应的系统进程对文件属主的要求。

常见的伪用户如下所示：

```
伪 用 户 含 义 
bin 拥有可执行的用户命令文件 
sys 拥有系统文件 
adm 拥有帐户文件 
uucp UUCP使用 
lp lp或lpd子系统使用 
nobody NFS使用
```





##### 2、拥有帐户文件



###### **1、除了上面列出的伪用户外，还有许多标准的伪用户，例如：audit, cron, mail, usenet等，它们也都各自为相关的进程和文件所需要。**

由于/etc/passwd文件是所有用户都可读的，如果用户的密码太简单或规律比较明显的话，一台普通的计算机就能够很容易地将它破解，因此对安全性要求较高的Linux系统都把加密后的口令字分离出来，单独存放在一个文件中，这个文件是/etc/shadow文件。 有超级用户才拥有该文件读权限，这就保证了用户密码的安全性。

###### **2、/etc/shadow中的记录行与/etc/passwd中的一一对应，它由pwconv命令根据/etc/passwd中的数据自动产生**

它的文件格式与/etc/passwd类似，由若干个字段组成，字段之间用":"隔开。这些字段是：

```
登录名:加密口令:最后一次修改时间:最小时间间隔:最大时间间隔:警告时间:不活动时间:失效时间:标志
```

1. "登录名"是与/etc/passwd文件中的登录名相一致的用户账号
2. "口令"字段存放的是加密后的用户口令字，长度为13个字符。如果为空，则对应用户没有口令，登录时不需要口令；如果含有不属于集合 { ./0-9A-Za-z }中的字符，则对应的用户不能登录。
3. "最后一次修改时间"表示的是从某个时刻起，到用户最后一次修改口令时的天数。时间起点对不同的系统可能不一样。例如在SCO Linux 中，这个时间起点是1970年1月1日。
4. "最小时间间隔"指的是两次修改口令之间所需的最小天数。
5. "最大时间间隔"指的是口令保持有效的最大天数。
6. "警告时间"字段表示的是从系统开始警告用户到用户密码正式失效之间的天数。
7. "不活动时间"表示的是用户没有登录活动但账号仍能保持有效的最大天数。
8. "失效时间"字段给出的是一个绝对的天数，如果使用了这个字段，那么就给出相应账号的生存期。期满后，该账号就不再是一个合法的账号，也就不能再用来登录了。

下面是/etc/shadow的一个例子：

```
＃ cat /etc/shadow

root:Dnakfw28zf38w:8764:0:168:7:::
daemon:*::0:0::::
bin:*::0:0::::
sys:*::0:0::::
adm:*::0:0::::
uucp:*::0:0::::
nuucp:*::0:0::::
auth:*::0:0::::
cron:*::0:0::::
listen:*::0:0::::
lp:*::0:0::::
sam:EkdiSECLWPdSa:9740:0:0::::
```

##### 3、用户组的所有信息都存放在/etc/group文件中。



将用户分组是Linux 系统中对用户进行管理及控制访问权限的一种手段。

每个用户都属于某个用户组；一个组中可以有多个用户，一个用户也可以属于不同的组。

当一个用户同时是多个组中的成员时，在/etc/passwd文件中记录的是用户所属的主组，也就是登录时所属的默认组，而其他组称为附加组。

用户要访问属于附加组的文件时，必须首先使用newgrp命令使自己成为所要访问的组中的成员。

用户组的所有信息都存放在/etc/group文件中。此文件的格式也类似于/etc/passwd文件，由冒号(:)隔开若干个字段，这些字段有：

```
组名:口令:组标识号:组内用户列表
```

1. "组名"是用户组的名称，由字母或数字构成。与/etc/passwd中的登录名一样，组名不应重复。
2. "口令"字段存放的是用户组加密后的口令字。一般Linux 系统的用户组都没有口令，即这个字段一般为空，或者是*。
3. "组标识号"与用户标识号类似，也是一个整数，被系统内部用来标识组。
4. "组内用户列表"是属于这个组的所有用户的列表，不同用户之间用逗号(,)分隔。这个用户组可能是用户的主组，也可能是附加组。

/etc/group文件的一个例子如下：

```
root::0:root
bin::2:root,bin
sys::3:root,uucp
adm::4:root,adm
daemon::5:root,daemon
lp::7:root,lp
users::20:root,sam
```

#### 四、添加批量用户

添加和删除用户对每位Linux系统管理员都是轻而易举的事，比较棘手的是如果要添加几十个、上百个甚至上千个用户时，我们不太可能还使用useradd一个一个地添加，必然要找一种简便的创建大量用户的方法。Linux系统提供了创建大量用户的工具，可以让您立即创建大量用户，方法如下：

##### （1）先编辑一个文本用户文件。

每一列按照`/etc/passwd`密码文件的格式书写，要注意每个用户的用户名、UID、宿主目录都不可以相同，其中密码栏可以留做空白或输入x号。一个范例文件user.txt内容如下：

```
user001::600:100:user:/home/user001:/bin/bash
user002::601:100:user:/home/user002:/bin/bash
user003::602:100:user:/home/user003:/bin/bash
user004::603:100:user:/home/user004:/bin/bash
user005::604:100:user:/home/user005:/bin/bash
user006::605:100:user:/home/user006:/bin/bash
```

##### （2）以root身份执行命令 `/usr/sbin/newusers`，从刚创建的用户文件`user.txt`中导入数据，创建用户：

```
# newusers < user.txt
```

然后可以执行命令 `vipw` 或 `vi /etc/passwd` 检查 `/etc/passwd` 文件是否已经出现这些用户的数据，并且用户的宿主目录是否已经创建。

##### （3）执行命令/usr/sbin/pwunconv。

将 `/etc/shadow` 产生的 `shadow` 密码解码，然后回写到 `/etc/passwd` 中，并将`/etc/shadow`的`shadow`密码栏删掉。这是为了方便下一步的密码转换工作，即先取消 `shadow password` 功能。

```
# pwunconv
```

##### （4）编辑每个用户的密码对照文件。

格式为：

```
用户名:密码
```

实例文件 `passwd.txt` 内容如下：

```
user001:123456
user002:123456
user003:123456
user004:123456
user005:123456
user006:123456
```

##### （5）以 root 身份执行命令 `/usr/sbin/chpasswd`。

创建用户密码，`chpasswd` 会将经过 `/usr/bin/passwd` 命令编码过的密码写入 `/etc/passwd` 的密码栏。

```
# chpasswd < passwd.txt
```

##### （6）确定密码经编码写入/etc/passwd的密码栏后。

执行命令 `/usr/sbin/pwconv` 将密码编码为 `shadow password`，并将结果写入 `/etc/shadow`。

```
# pwconv
```

这样就完成了大量用户的创建了，之后您可以到/home下检查这些用户宿主目录的权限设置是否都正确，并登录验证用户密码是否正确。



### 6、 磁盘管理



Linux 磁盘管理好坏直接关系到整个系统的性能问题。

Linux 磁盘管理常用三个命令为 **df**、**du** 和 **fdisk**。

- **df**（英文全称：disk full）：列出文件系统的整体磁盘使用量
- **du**（英文全称：disk used）：检查磁盘空间使用量
- **fdisk**：用于磁盘分区



#### df

df命令参数功能：检查文件系统的磁盘空间占用情况。可以利用该命令来获取硬盘被占用了多少空间，目前还剩下多少空间等信息。

语法：

```
df [-ahikHTm] [目录或文件名]
```

选项与参数：

- -a ：列出所有的文件系统，包括系统特有的 /proc 等文件系统；
- -k ：以 KBytes 的容量显示各文件系统；
- -m ：以 MBytes 的容量显示各文件系统；
- -h ：以人们较易阅读的 GBytes, MBytes, KBytes 等格式自行显示；
- -H ：以 M=1000K 取代 M=1024K 的进位方式；
- -T ：显示文件系统类型, 连同该 partition 的 filesystem 名称 (例如 ext3) 也列出；
- -i ：不用硬盘容量，而以 inode 的数量来显示

##### 实例 1

将系统内所有的文件系统列出来！

```
[root@www ~]# df
Filesystem      1K-blocks      Used Available Use% Mounted on
/dev/hdc2         9920624   3823112   5585444  41% /
/dev/hdc3         4956316    141376   4559108   4% /home
/dev/hdc1          101086     11126     84741  12% /boot
tmpfs              371332         0    371332   0% /dev/shm
```

在 Linux 底下如果 df 没有加任何选项，那么默认会将系统内所有的 (不含特殊内存内的文件系统与 swap) 都以 1 Kbytes 的容量来列出来！

##### 实例 2

将容量结果以易读的容量格式显示出来

```
[root@www ~]# df -h
Filesystem            Size  Used Avail Use% Mounted on
/dev/hdc2             9.5G  3.7G  5.4G  41% /
/dev/hdc3             4.8G  139M  4.4G   4% /home
/dev/hdc1              99M   11M   83M  12% /boot
tmpfs                 363M     0  363M   0% /dev/shm
```

##### 实例 3

将系统内的所有特殊文件格式及名称都列出来

```
[root@www ~]# df -aT
Filesystem    Type 1K-blocks    Used Available Use% Mounted on
/dev/hdc2     ext3   9920624 3823112   5585444  41% /
proc          proc         0       0         0   -  /proc
sysfs        sysfs         0       0         0   -  /sys
devpts      devpts         0       0         0   -  /dev/pts
/dev/hdc3     ext3   4956316  141376   4559108   4% /home
/dev/hdc1     ext3    101086   11126     84741  12% /boot
tmpfs        tmpfs    371332       0    371332   0% /dev/shm
none   binfmt_misc         0       0         0   -  /proc/sys/fs/binfmt_misc
sunrpc  rpc_pipefs         0       0         0   -  /var/lib/nfs/rpc_pipefs
```

##### 实例 4

将 /etc 底下的可用的磁盘容量以易读的容量格式显示

```
[root@www ~]# df -h /etc
Filesystem            Size  Used Avail Use% Mounted on
/dev/hdc2             9.5G  3.7G  5.4G  41% /
```



#### du

Linux du 命令也是查看使用空间的，但是与 df 命令不同的是 Linux du 命令是对文件和目录磁盘使用的空间的查看，还是和df命令有一些区别的，这里介绍 Linux du 命令。

语法：

```
du [-ahskm] 文件或目录名称
```

选项与参数：

- -a ：列出所有的文件与目录容量，因为默认仅统计目录底下的文件量而已。
- -h ：以人们较易读的容量格式 (G/M) 显示；
- -s ：列出总量而已，而不列出每个各别的目录占用容量；
- -S ：不包括子目录下的总计，与 -s 有点差别。
- -k ：以 KBytes 列出容量显示；
- -m ：以 MBytes 列出容量显示；

##### 实例 1

只列出当前目录下的所有文件夹容量（包括隐藏文件夹）:

```
[root@www ~]# du
8       ./test4     <==每个目录都会列出来
8       ./test2
....中间省略....
12      ./.gconfd   <==包括隐藏文件的目录
220     .           <==这个目录(.)所占用的总量
```

直接输入 du 没有加任何选项时，则 du 会分析当前所在目录里的子目录所占用的硬盘空间。

##### 实例 2

将文件的容量也列出来

```
[root@www ~]# du -a
12      ./install.log.syslog   <==有文件的列表了
8       ./.bash_logout
8       ./test4
8       ./test2
....中间省略....
12      ./.gconfd
220     .
```

##### 实例 3

检查根目录底下每个目录所占用的容量

```
[root@www ~]# du -sm /*
7       /bin
6       /boot
.....中间省略....
0       /proc
.....中间省略....
1       /tmp
3859    /usr     <==系统初期最大就是他了啦！
77      /var
```

通配符 * 来代表每个目录。

与 df 不一样的是，du 这个命令其实会直接到文件系统内去搜寻所有的文件数据。



#### fdisk



fdisk 是 Linux 的磁盘分区表操作工具。

语法：

```
fdisk [-l] 装置名称
```

选项与参数：

- -l ：输出后面接的装置所有的分区内容。若仅有 fdisk -l 时， 则系统将会把整个系统内能够搜寻到的装置的分区均列出来。

##### 实例 1

列出所有分区信息

```
[root@AY120919111755c246621 tmp]# fdisk -l

Disk /dev/xvda: 21.5 GB, 21474836480 bytes
255 heads, 63 sectors/track, 2610 cylinders
Units = cylinders of 16065 * 512 = 8225280 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes
Disk identifier: 0x00000000

    Device Boot      Start         End      Blocks   Id  System
/dev/xvda1   *           1        2550    20480000   83  Linux
/dev/xvda2            2550        2611      490496   82  Linux swap / Solaris

Disk /dev/xvdb: 21.5 GB, 21474836480 bytes
255 heads, 63 sectors/track, 2610 cylinders
Units = cylinders of 16065 * 512 = 8225280 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes
Disk identifier: 0x56f40944

    Device Boot      Start         End      Blocks   Id  System
/dev/xvdb2               1        2610    20964793+  83  Linux
```

##### 实例 2

找出你系统中的根目录所在磁盘，并查阅该硬盘内的相关信息

```
[root@www ~]# df /            <==注意：重点在找出磁盘文件名而已
Filesystem           1K-blocks      Used Available Use% Mounted on
/dev/hdc2              9920624   3823168   5585388  41% /

[root@www ~]# fdisk /dev/hdc  <==仔细看，不要加上数字喔！
The number of cylinders for this disk is set to 5005.
There is nothing wrong with that, but this is larger than 1024,
and could in certain setups cause problems with:
1) software that runs at boot time (e.g., old versions of LILO)
2) booting and partitioning software from other OSs
   (e.g., DOS FDISK, OS/2 FDISK)

Command (m for help):     <==等待你的输入！
```

输入 m 后，就会看到底下这些命令介绍

```
Command (m for help): m   <== 输入 m 后，就会看到底下这些命令介绍
Command action
   a   toggle a bootable flag
   b   edit bsd disklabel
   c   toggle the dos compatibility flag
   d   delete a partition            <==删除一个partition
   l   list known partition types
   m   print this menu
   n   add a new partition           <==新增一个partition
   o   create a new empty DOS partition table
   p   print the partition table     <==在屏幕上显示分割表
   q   quit without saving changes   <==不储存离开fdisk程序
   s   create a new empty Sun disklabel
   t   change a partition's system id
   u   change display/entry units
   v   verify the partition table
   w   write table to disk and exit  <==将刚刚的动作写入分割表
   x   extra functionality (experts only)
```

离开 fdisk 时按下 `q`，那么所有的动作都不会生效！相反的， 按下`w`就是动作生效的意思。

```
Command (m for help): p  <== 这里可以输出目前磁盘的状态

Disk /dev/hdc: 41.1 GB, 41174138880 bytes        <==这个磁盘的文件名与容量
255 heads, 63 sectors/track, 5005 cylinders      <==磁头、扇区与磁柱大小
Units = cylinders of 16065 * 512 = 8225280 bytes <==每个磁柱的大小

   Device Boot      Start         End      Blocks   Id  System
/dev/hdc1   *           1          13      104391   83  Linux
/dev/hdc2              14        1288    10241437+  83  Linux
/dev/hdc3            1289        1925     5116702+  83  Linux
/dev/hdc4            1926        5005    24740100    5  Extended
/dev/hdc5            1926        2052     1020096   82  Linux swap / Solaris
# 装置文件名 启动区否 开始磁柱    结束磁柱  1K大小容量 磁盘分区槽内的系统

Command (m for help): q
```

想要不储存离开吗？按下 q 就对了！不要随便按 w 啊！

使用 `p` 可以列出目前这颗磁盘的分割表信息，这个信息的上半部在显示整体磁盘的状态。



#### 磁盘格式化

磁盘分割完毕后自然就是要进行文件系统的格式化，格式化的命令非常的简单，使用 `mkfs`（make filesystem） 命令。

语法：

```
mkfs [-t 文件系统格式] 装置文件名
```

选项与参数：

- -t ：可以接文件系统格式，例如 ext3, ext2, vfat 等(系统有支持才会生效)

##### 实例 1

查看 mkfs 支持的文件格式

```
[root@www ~]# mkfs[tab][tab]
mkfs         mkfs.cramfs  mkfs.ext2    mkfs.ext3    mkfs.msdos   mkfs.vfat
```

按下两个[tab]，会发现 mkfs 支持的文件格式如上所示。

##### 实例 2

将分区 /dev/hdc6（可指定你自己的分区） 格式化为 ext3 文件系统：

```
[root@www ~]# mkfs -t ext3 /dev/hdc6
mke2fs 1.39 (29-May-2006)
Filesystem label=                <==这里指的是分割槽的名称(label)
OS type: Linux
Block size=4096 (log=2)          <==block 的大小配置为 4K 
Fragment size=4096 (log=2)
251392 inodes, 502023 blocks     <==由此配置决定的inode/block数量
25101 blocks (5.00%) reserved for the super user
First data block=0
Maximum filesystem blocks=515899392
16 block groups
32768 blocks per group, 32768 fragments per group
15712 inodes per group
Superblock backups stored on blocks:
        32768, 98304, 163840, 229376, 294912

Writing inode tables: done
Creating journal (8192 blocks): done <==有日志记录
Writing superblocks and filesystem accounting information: done

This filesystem will be automatically checked every 34 mounts or
180 days, whichever comes first.  Use tune2fs -c or -i to override.
# 这样就创建起来我们所需要的 Ext3 文件系统了！简单明了！
```



#### 磁盘检验



fsck（file system check）用来检查和维护不一致的文件系统。

若系统掉电或磁盘发生问题，可利用fsck命令对文件系统进行检查。

语法：

```
fsck [-t 文件系统] [-ACay] 装置名称
```

选项与参数：

- -t : 给定档案系统的型式，若在 /etc/fstab 中已有定义或 kernel 本身已支援的则不需加上此参数
- -s : 依序一个一个地执行 fsck 的指令来检查
- -A : 对/etc/fstab 中所有列出来的 分区（partition）做检查
- -C : 显示完整的检查进度
- -d : 打印出 e2fsck 的 debug 结果
- -p : 同时有 -A 条件时，同时有多个 fsck 的检查一起执行
- -R : 同时有 -A 条件时，省略 / 不检查
- -V : 详细显示模式
- -a : 如果检查有错则自动修复
- -r : 如果检查有错则由使用者回答是否修复
- -y : 选项指定检测每个文件是自动输入yes，在不确定那些是不正常的时候，可以执行 # fsck -y 全部检查修复。

##### 实例 1

查看系统有多少文件系统支持的 fsck 命令：

```
[root@www ~]# fsck[tab][tab]
fsck         fsck.cramfs  fsck.ext2    fsck.ext3    fsck.msdos   fsck.vfat
```

##### 实例 2

强制检测 /dev/hdc6 分区:

```
[root@www ~]# fsck -C -f -t ext3 /dev/hdc6 
fsck 1.39 (29-May-2006)
e2fsck 1.39 (29-May-2006)
Pass 1: Checking inodes, blocks, and sizes
Pass 2: Checking directory structure
Pass 3: Checking directory connectivity
Pass 4: Checking reference counts
Pass 5: Checking group summary information
vbird_logical: 11/251968 files (9.1% non-contiguous), 36926/1004046 blocks
```

如果没有加上 -f 的选项，则由于这个文件系统不曾出现问题，检查的经过非常快速！若加上 -f 强制检查，才会一项一项的显示过程。



#### 磁盘挂载与卸除



Linux 的磁盘挂载使用 `mount` 命令，卸载使用 `umount` 命令。

磁盘挂载语法：

```
mount [-t 文件系统] [-L Label名] [-o 额外选项] [-n]  装置文件名  挂载点
```

##### 实例 1

用默认的方式，将刚刚创建的 /dev/hdc6 挂载到 /mnt/hdc6 上面！

```
[root@www ~]# mkdir /mnt/hdc6
[root@www ~]# mount /dev/hdc6 /mnt/hdc6
[root@www ~]# df
Filesystem           1K-blocks      Used Available Use% Mounted on
.....中间省略.....
/dev/hdc6              1976312     42072   1833836   3% /mnt/hdc6
```

磁盘卸载命令 `umount` 语法：

```
umount [-fn] 装置文件名或挂载点
```

选项与参数：

- -f ：强制卸除！可用在类似网络文件系统 (NFS) 无法读取到的情况下；
- -n ：不升级 /etc/mtab 情况下卸除。

卸载/dev/hdc6

```
[root@www ~]# umount /dev/hdc6     
```







### 7、vi/vim

所有的 Unix Like 系统都会内建 vi 文书编辑器，其他的文书编辑器则不一定会存在。

但是目前我们使用比较多的是 vim 编辑器。

vim 具有程序编辑的能力，可以主动的以字体颜色辨别语法的正确性，方便程序设计。

相关文章：[史上最全Vim快捷键键位图 — 入门到进阶](https://www.runoob.com/w3cnote/all-vim-cheatsheat.html)



#### 什么是 vim？



Vim是从 vi 发展出来的一个文本编辑器。代码补完、编译及错误跳转等方便编程的功能特别丰富，在程序员中被广泛使用。

简单的来说， vi 是老式的字处理器，不过功能已经很齐全了，但是还是有可以进步的地方。 vim 则可以说是程序开发者的一项很好用的工具。

连 vim 的官方网站 ([http://www.vim.org](http://www.vim.org/)) 自己也说 vim 是一个程序开发工具而不是文字处理软件。

vim 键盘图：

![img](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/vi-vim-cheat-sheet-sch.gif)



#### vi/vim 的使用

基本上 vi/vim 共分为三种模式，分别是**命令模式（Command mode）**，**输入模式（Insert mode）**和**底线命令模式（Last line mode）**。 这三种模式的作用分别是：

##### 命令模式：

用户刚刚启动 vi/vim，便进入了命令模式。

此状态下敲击键盘动作会被Vim识别为命令，而非输入字符。比如我们此时按下i，并不会输入一个字符，i被当作了一个命令。

以下是常用的几个命令：

- **i** 切换到输入模式，以输入字符。
- **x** 删除当前光标所在处的字符。
- **:** 切换到底线命令模式，以在最底一行输入命令。

若想要编辑文本：启动Vim，进入了命令模式，按下i，切换到输入模式。

命令模式只有一些最基本的命令，因此仍要依靠底线命令模式输入更多命令。

##### 输入模式

在命令模式下按下i就进入了输入模式。

在输入模式中，可以使用以下按键：

- **字符按键以及Shift组合**，输入字符
- **ENTER**，回车键，换行
- **BACK SPACE**，退格键，删除光标前一个字符
- **DEL**，删除键，删除光标后一个字符
- **方向键**，在文本中移动光标
- **HOME**/**END**，移动光标到行首/行尾
- **Page Up**/**Page Down**，上/下翻页
- **Insert**，切换光标为输入/替换模式，光标将变成竖线/下划线
- **ESC**，退出输入模式，切换到命令模式

##### 底线命令模式

在命令模式下按下:（英文冒号）就进入了底线命令模式。

底线命令模式可以输入单个或多个字符的命令，可用的命令非常多。

在底线命令模式中，基本的命令有（已经省略了冒号）：

- q 退出程序
- w 保存文件

按ESC键可随时退出底线命令模式。

简单的说，我们可以将这三个模式想成底下的图标来表示：

![img](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/vim-vi-workmodel.png)



#### vi/vim 使用实例



##### 使用 vi/vim 进入一般模式

如果你想要使用 vi 来建立一个名为 runoob.txt 的文件时，你可以这样做：

```
$ vim runoob.txt
```

直接输入 **vi 文件名** 就能够进入 vi 的一般模式了。请注意，记得 vi 后面一定要加文件名，不管该文件存在与否！

![img](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/078207F0-B204-4464-AAEF-982F45EDDAE9.jpg)

##### 按下 i 进入输入模式(也称为编辑模式)，开始编辑文字

在一般模式之中，只要按下 i, o, a 等字符就可以进入输入模式了！

在编辑模式当中，你可以发现在左下角状态栏中会出现 –INSERT- 的字样，那就是可以输入任意字符的提示。

这个时候，键盘上除了 **Esc** 这个按键之外，其他的按键都可以视作为一般的输入按钮了，所以你可以进行任何的编辑。

![img](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/1C928383-471E-4AF1-A61E-9E2CCBD5A913.jpg)

##### 按下 ESC 按钮回到一般模式

好了，假设我已经按照上面的样式给他编辑完毕了，那么应该要如何退出呢？是的！没错！就是给他按下 **Esc** 这个按钮即可！马上你就会发现画面左下角的 – INSERT – 不见了！

##### 在一般模式中按下 **:wq** 储存后离开 vi

OK，我们要存档了，存盘并离开的指令很简单，输入 **:wq** 即可保存离开！

![img](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/B2FB5146-327C-4019-AC96-DD7A8EE7460C.jpg)

OK! 这样我们就成功创建了一个 runoob.txt 的文件。



#### vi/vim 按键说明

除了上面简易范例的 i, Esc, :wq 之外，其实 vim 还有非常多的按键可以使用。

##### 第一部分：一般模式可用的光标移动、复制粘贴、搜索替换等

| 移动光标的方法                                               |                                                              |
| :----------------------------------------------------------- | ------------------------------------------------------------ |
| h 或 向左箭头键(←)                                           | 光标向左移动一个字符                                         |
| j 或 向下箭头键(↓)                                           | 光标向下移动一个字符                                         |
| k 或 向上箭头键(↑)                                           | 光标向上移动一个字符                                         |
| l 或 向右箭头键(→)                                           | 光标向右移动一个字符                                         |
| 如果你将右手放在键盘上的话，你会发现 hjkl 是排列在一起的，因此可以使用这四个按钮来移动光标。 如果想要进行多次移动的话，例如向下移动 30 行，可以使用 "30j" 或 "30↓" 的组合按键， 亦即加上想要进行的次数(数字)后，按下动作即可！ |                                                              |
| [Ctrl] + [f]                                                 | 屏幕『向下』移动一页，相当于 [Page Down]按键 (常用)          |
| [Ctrl] + [b]                                                 | 屏幕『向上』移动一页，相当于 [Page Up] 按键 (常用)           |
| [Ctrl] + [d]                                                 | 屏幕『向下』移动半页                                         |
| [Ctrl] + [u]                                                 | 屏幕『向上』移动半页                                         |
| +                                                            | 光标移动到非空格符的下一行                                   |
| -                                                            | 光标移动到非空格符的上一行                                   |
| n<space>                                                     | 那个 n 表示『数字』，例如 20 。按下数字后再按空格键，光标会向右移动这一行的 n 个字符。例如 20<space> 则光标会向后面移动 20 个字符距离。 |
| 0 或功能键[Home]                                             | 这是数字『 0 』：移动到这一行的最前面字符处 (常用)           |
| $ 或功能键[End]                                              | 移动到这一行的最后面字符处(常用)                             |
| H                                                            | 光标移动到这个屏幕的最上方那一行的第一个字符                 |
| M                                                            | 光标移动到这个屏幕的中央那一行的第一个字符                   |
| L                                                            | 光标移动到这个屏幕的最下方那一行的第一个字符                 |
| G                                                            | 移动到这个档案的最后一行(常用)                               |
| nG                                                           | n 为数字。移动到这个档案的第 n 行。例如 20G 则会移动到这个档案的第 20 行(可配合 :set nu) |
| gg                                                           | 移动到这个档案的第一行，相当于 1G 啊！ (常用)                |
| n<Enter>                                                     | n 为数字。光标向下移动 n 行(常用)                            |
| 搜索替换                                                     |                                                              |
| /word                                                        | 向光标之下寻找一个名称为 word 的字符串。例如要在档案内搜寻 vbird 这个字符串，就输入 /vbird 即可！ (常用) |
| ?word                                                        | 向光标之上寻找一个字符串名称为 word 的字符串。               |
| n                                                            | 这个 n 是英文按键。代表重复前一个搜寻的动作。举例来说， 如果刚刚我们执行 /vbird 去向下搜寻 vbird 这个字符串，则按下 n 后，会向下继续搜寻下一个名称为 vbird 的字符串。如果是执行 ?vbird 的话，那么按下 n 则会向上继续搜寻名称为 vbird 的字符串！ |
| N                                                            | 这个 N 是英文按键。与 n 刚好相反，为『反向』进行前一个搜寻动作。 例如 /vbird 后，按下 N 则表示『向上』搜寻 vbird 。 |
| 使用 /word 配合 n 及 N 是非常有帮助的！可以让你重复的找到一些你搜寻的关键词！ |                                                              |
| :n1,n2s/word1/word2/g                                        | n1 与 n2 为数字。在第 n1 与 n2 行之间寻找 word1 这个字符串，并将该字符串取代为 word2 ！举例来说，在 100 到 200 行之间搜寻 vbird 并取代为 VBIRD 则： 『:100,200s/vbird/VBIRD/g』。(常用) |
| **:1,$s/word1/word2/g** 或 **:%s/word1/word2/g**             | 从第一行到最后一行寻找 word1 字符串，并将该字符串取代为 word2 ！(常用) |
| **:1,$s/word1/word2/gc** 或 **:%s/word1/word2/gc**           | 从第一行到最后一行寻找 word1 字符串，并将该字符串取代为 word2 ！且在取代前显示提示字符给用户确认 (confirm) 是否需要取代！(常用) |
| 删除、复制与贴上                                             |                                                              |
| x, X                                                         | 在一行字当中，x 为向后删除一个字符 (相当于 [del] 按键)， X 为向前删除一个字符(相当于 [backspace] 亦即是退格键) (常用) |
| nx                                                           | n 为数字，连续向后删除 n 个字符。举例来说，我要连续删除 10 个字符， 『10x』。 |
| dd                                                           | 删除游标所在的那一整行(常用)                                 |
| ndd                                                          | n 为数字。删除光标所在的向下 n 行，例如 20dd 则是删除 20 行 (常用) |
| d1G                                                          | 删除光标所在到第一行的所有数据                               |
| dG                                                           | 删除光标所在到最后一行的所有数据                             |
| d$                                                           | 删除游标所在处，到该行的最后一个字符                         |
| d0                                                           | 那个是数字的 0 ，删除游标所在处，到该行的最前面一个字符      |
| yy                                                           | 复制游标所在的那一行(常用)                                   |
| nyy                                                          | n 为数字。复制光标所在的向下 n 行，例如 20yy 则是复制 20 行(常用) |
| y1G                                                          | 复制游标所在行到第一行的所有数据                             |
| yG                                                           | 复制游标所在行到最后一行的所有数据                           |
| y0                                                           | 复制光标所在的那个字符到该行行首的所有数据                   |
| y$                                                           | 复制光标所在的那个字符到该行行尾的所有数据                   |
| p, P                                                         | p 为将已复制的数据在光标下一行贴上，P 则为贴在游标上一行！ 举例来说，我目前光标在第 20 行，且已经复制了 10 行数据。则按下 p 后， 那 10 行数据会贴在原本的 20 行之后，亦即由 21 行开始贴。但如果是按下 P 呢？ 那么原本的第 20 行会被推到变成 30 行。 (常用) |
| J                                                            | 将光标所在行与下一行的数据结合成同一行                       |
| c                                                            | 重复删除多个数据，例如向下删除 10 行，[ 10cj ]               |
| u                                                            | 复原前一个动作。(常用)                                       |
| [Ctrl]+r                                                     | 重做上一个动作。(常用)                                       |
| 这个 u 与 [Ctrl]+r 是很常用的指令！一个是复原，另一个则是重做一次～ 利用这两个功能按键，你的编辑，嘿嘿！很快乐的啦！ |                                                              |
| .                                                            | 不要怀疑！这就是小数点！意思是重复前一个动作的意思。 如果你想要重复删除、重复贴上等等动作，按下小数点『.』就好了！ (常用) |

##### 第二部分：一般模式切换到编辑模式的可用的按钮说明

| 进入输入或取代的编辑模式                                     |                                                              |
| :----------------------------------------------------------- | ------------------------------------------------------------ |
| i, I                                                         | 进入输入模式(Insert mode)： i 为『从目前光标所在处输入』， I 为『在目前所在行的第一个非空格符处开始输入』。 (常用) |
| a, A                                                         | 进入输入模式(Insert mode)： a 为『从目前光标所在的下一个字符处开始输入』， A 为『从光标所在行的最后一个字符处开始输入』。(常用) |
| o, O                                                         | 进入输入模式(Insert mode)： 这是英文字母 o 的大小写。o 为在目前光标所在的下一行处输入新的一行； O 为在目前光标所在的上一行处输入新的一行！(常用) |
| r, R                                                         | 进入取代模式(Replace mode)： r 只会取代光标所在的那一个字符一次；R会一直取代光标所在的文字，直到按下 ESC 为止；(常用) |
| 上面这些按键中，在 vi 画面的左下角处会出现『--INSERT--』或『--REPLACE--』的字样。 由名称就知道该动作了吧！！特别注意的是，我们上面也提过了，你想要在档案里面输入字符时， 一定要在左下角处看到 INSERT 或 REPLACE 才能输入喔！ |                                                              |
| [Esc]                                                        | 退出编辑模式，回到一般模式中(常用)                           |

##### 第三部分：一般模式切换到指令行模式的可用的按钮说明

| 指令行的储存、离开等指令                                     |                                                              |
| :----------------------------------------------------------- | ------------------------------------------------------------ |
| :w                                                           | 将编辑的数据写入硬盘档案中(常用)                             |
| :w!                                                          | 若文件属性为『只读』时，强制写入该档案。不过，到底能不能写入， 还是跟你对该档案的档案权限有关啊！ |
| :q                                                           | 离开 vi (常用)                                               |
| :q!                                                          | 若曾修改过档案，又不想储存，使用 ! 为强制离开不储存档案。    |
| 注意一下啊，那个惊叹号 (!) 在 vi 当中，常常具有『强制』的意思～ |                                                              |
| :wq                                                          | 储存后离开，若为 :wq! 则为强制储存后离开 (常用)              |
| ZZ                                                           | 这是大写的 Z 喔！如果修改过，保存当前文件，然后退出！效果等同于(保存并退出) |
| ZQ                                                           | 不保存，强制退出。效果等同于 **:q!**。                       |
| :w [filename]                                                | 将编辑的数据储存成另一个档案（类似另存新档）                 |
| :r [filename]                                                | 在编辑的数据中，读入另一个档案的数据。亦即将 『filename』 这个档案内容加到游标所在行后面 |
| :n1,n2 w [filename]                                          | 将 n1 到 n2 的内容储存成 filename 这个档案。                 |
| :! command                                                   | 暂时离开 vi 到指令行模式下执行 command 的显示结果！例如 『:! ls /home』即可在 vi 当中察看 /home 底下以 ls 输出的档案信息！ |
| vim 环境的变更                                               |                                                              |
| :set nu                                                      | 显示行号，设定之后，会在每一行的前缀显示该行的行号           |
| :set nonu                                                    | 与 set nu 相反，为取消行号！                                 |

特别注意，在 vi/vim 中，数字是很有意义的！数字通常代表重复做几次的意思！ 也有可能是代表去到第几个什么什么的意思。

举例来说，要删除 50 行，则是用 『50dd』 对吧！ 数字加在动作之前，如我要向下移动 20 行呢？那就是『20j』或者是『20↓』即可。



### 7、apt 命令



**Centos apt 改为 yum**

apt（Advanced Packaging Tool）是一个在 Debian 和 Ubuntu 中的 Shell 前端软件包管理器。

apt 命令提供了查找、安装、升级、删除某一个、一组甚至全部软件包的命令，而且命令简洁而又好记。

apt 命令执行需要超级管理员权限(root)。

#### apt 语法

```
  apt [options] [command] [package ...]
```

- **options：**可选，选项包括 -h（帮助），-y（当安装过程提示选择全部为"yes"），-q（不显示安装的过程）等等。
- **command：**要进行的操作。
- **package**：安装的包名。



#### apt 常用命令



- 列出所有可更新的软件清单命令：**sudo apt update**

- 升级软件包：**sudo apt upgrade**

  列出可更新的软件包及版本信息：**apt list --upgradeable**

  升级软件包，升级前先删除需要更新软件包：**sudo apt full-upgrade**

- 安装指定的软件命令：**sudo apt install <package_name>**

  安装多个软件包：**sudo apt install <package_1> <package_2> <package_3>**

- 更新指定的软件命令：**sudo apt update <package_name>**

- 显示软件包具体信息,例如：版本号，安装大小，依赖关系等等：**sudo apt show <package_name>**

- 删除软件包命令：**sudo apt remove <package_name>**

- 清理不再使用的依赖和库文件: **sudo apt autoremove**

- 移除软件包及配置文件: **sudo apt purge <package_name>**

- 查找软件包命令： **sudo apt search <keyword>**

- 列出所有已安装的包：**apt list --installed**

- 列出所有已安装的包的版本信息：**apt list --all-versions**

##### 实例

查看一些可更新的包：

```
sudo apt update
```

![img](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/apt-commands-examples.png)

升级安装包：

```
sudo apt upgrade
```

![img](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/apt-commands-examples-1.png)

在以上交互式输入字母 **Y** 即可开始升级。

可以将以下两个命令组合起来，一键升级：

```
sudo apt update && sudo apt upgrade -y
```

安装 mplayer 包：

```
sudo apt install mplayer
```

![img](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/apt-commands-examples-3.png)

如过不太记得完整的包名，我们可以只输入前半部分的包名，然后按下 **Tab** 键，会列出相关的包名：

![img](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/apt-commands-examples-2.png)

以上实例我们输入来 **reds**，然后按下 **Tab** 键，输出来四个相关的包。

如果我们想安装一个软件包，但如果软件包已经存在，则不要升级它，可以使用 **–no-upgrade** 选项:

```
sudo apt install <package_name> --no-upgrade
```

安装 mplayer 如果存在则不要升级：

```
sudo apt install mplayer --no-upgrade
```

![img](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/apt-commands-examples-4.png)

如果只想升级，不要安装可以使用 **--only-upgrade** 参数：

```
sudo apt install <package_name> --only-upgrade
```

只升级 mplayer，如果不存在就不要安装它：

```
sudo apt install mplayer --only-upgrade
```

![img](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/apt-commands-examples-5.png)

如果需要设置指定版本，语法格式如下：

```
sudo apt install <package_name>=<version_number>
```

**package_name** 为包名，**version_number** 为版本号。

移除包可以使用 remove 命令：

```
sudo apt remove mplayer
```

![img](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/apt-commands-examples-6-e1499720021872.png)

查找名为 libimobile 的相关包：

```
apt search libimobile
```

![img](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/apt-commands-examples-8.png)

查看 pinta 包的相关信息：

```
apt show pinta
```

![img](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/apt-commands-examples-7.png)

列出可更新的软件包：

```
apt list --upgradeable
```

![img](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/apt-commands-examples-9.png)

清理不再使用的依赖和库文件：

```
sudo apt autoremove
```

![img](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/apt-commands-examples-10.png)

在以上交互式输入字母 **Y** 即可开始清理。





## 二、问题



### 1、E45: 'readonly' option is set (add ! to override)

```shell
:wq!  强制保存并退出
```



















# Docker 笔记

## 简介

![img](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/docker01.png)

Docker 是一个开源的应用容器引擎，基于 [Go 语言](https://www.runoob.com/go/go-tutorial.html) 并遵从 Apache2.0 协议开源。

Docker 可以让开发者打包他们的应用以及依赖包到一个轻量级、可移植的容器中，然后发布到任何流行的 Linux 机器上，也可以实现虚拟化。

容器是完全使用沙箱机制，相互之间不会有任何接口（类似 iPhone 的 app）,更重要的是容器性能开销极低。

Docker 从 17.03 版本之后分为 CE（Community Edition: 社区版） 和 EE（Enterprise Edition: 企业版），我们用社区版就可以了。



## CentOS Docker 安装

### **使用官方安装脚本自动安装**

安装命令如下：

```
curl -fsSL https://get.docker.com | bash -s docker --mirror Aliyun
```

也可以使用国内 daocloud 一键安装命令：

```
curl -sSL https://get.daocloud.io/docker | sh
```

------

### **手动安装**

#### **卸载旧版本**

较旧的 Docker 版本称为 docker 或 docker-engine 。如果已安装这些程序，请卸载它们以及相关的依赖项。

```
$ sudo yum remove docker \
         docker-client \
         docker-client-latest \
         docker-common \
         docker-latest \
         docker-latest-logrotate \
         docker-logrotate \
         docker-engine
```

#### **安装 Docker Engine-Community**

#### **使用 Docker 仓库进行安装**

在新主机上首次安装 Docker Engine-Community 之前，需要设置 Docker 仓库。之后，您可以从仓库安装和更新 Docker。

**设置仓库**

安装所需的软件包。yum-utils 提供了 yum-config-manager ，并且 device mapper 存储驱动程序需要 device-mapper-persistent-data 和 lvm2。

$ **sudo** **yum install** -y yum-utils \
 device-mapper-persistent-data \
 lvm2

使用以下命令来设置稳定的仓库。

#### **使用官方源地址（比较慢）**

```
$ sudo yum-config-manager \
    --add-repo \
    https://download.docker.com/linux/centos/docker-ce.repo
```

可以选择国内的一些源地址：

#### **阿里云**

```
$ sudo yum-config-manager \
    --add-repo \
    http://mirrors.aliyun.com/docker-ce/linux/centos/docker-ce.repo
```

#### **清华大学源**

```
$ sudo yum-config-manager \
    --add-repo \
    https://mirrors.tuna.tsinghua.edu.cn/docker-ce/linux/centos/docker-ce.repo
```

#### **安装 Docker Engine-Community**

安装最新版本的 Docker Engine-Community 和 containerd，或者转到下一步安装特定版本：

```
$ sudo yum install docker-ce docker-ce-cli containerd.io
```

如果提示您接受 GPG 密钥，请选是。

> **有多个 Docker 仓库吗？**
>
> 如果启用了多个 Docker 仓库，则在未在 yum install 或 yum update 命令中指定版本的情况下，进行的安装或更新将始终安装最高版本，这可能不适合您的稳定性需求。

Docker 安装完默认未启动。并且已经创建好 docker 用户组，但该用户组下没有用户。

**要安装特定版本的 Docker Engine-Community，请在存储库中列出可用版本，然后选择并安装：**

1、列出并排序您存储库中可用的版本。此示例按版本号（从高到低）对结果进行排序。

$ **yum list** docker-ce --showduplicates **|** **sort** -r

docker-ce.x86_64  3:18.09.1-3.el7           docker-ce-stable
docker-ce.x86_64  3:18.09.0-3.el7           docker-ce-stable
docker-ce.x86_64  18.06.1.ce-3.el7           docker-ce-stable
docker-ce.x86_64  18.06.0.ce-3.el7           docker-ce-stable

2、通过其完整的软件包名称安装特定版本，该软件包名称是软件包名称（docker-ce）加上版本字符串（第二列），从第一个冒号（:）一直到第一个连字符，并用连字符（-）分隔。例如：docker-ce-18.09.1。

```
$ sudo yum install docker-ce-<VERSION_STRING> docker-ce-cli-<VERSION_STRING> containerd.io
```

启动 Docker。

```
$ sudo systemctl start docker
```

通过运行 hello-world 映像来验证是否正确安装了 Docker Engine-Community 。

```
$ sudo docker run hello-world
```

#### **卸载 docker**

#### **启动并加入开机启动**

```
$ sudo systemctl start docker
$ sudo systemctl enable docker
```

**删除安装包：**

```
yum remove docker-ce
```

**删除镜像、容器、配置文件等内容：**

```
rm -rf /var/lib/docker
```

#### **Docker 基本命令**

1、启动或停止docker命令

```
sudo service docker start 启动docker centos6.x的命令sudo service docker restart 重启docker centos6.x的命令sudo service docker stop 关闭docker centos6.x的命令sudo systemctl start docker 启动docker centos7.x 命令sudo systemctl restart  docker 重启docker centos7.x 命令sudo systemctl stop docker 关闭docker centos7.x 命令
```

2、查看docker版本

```
docker -v
```

3、查看docker下载的镜像

```
sudo docker images
```

![9a0eed828034a8c16a8d796922353ca3.png](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/9a0eed828034a8c16a8d796922353ca3.png)

4、設置docker开机自启动

```
sudo systemctl enable docker
```

5、查看容器启动日志

```
①、docker logs -f -t --tail 10 smartbus #实时查看docker容器名为smartbus的最后10行日志②、docker logs -f -t --since="2020-08-06" --tail=100 smartbus #查看指定时间后的日志，只显示最后100行③、docker logs --since 30m smartbus #查看最近30分钟的日志④、docker logs -t --since="2020-08-06T13:13:13" smartbus #查看某时间之后的日志⑤、docker logs -t --since="2020-08-01T13:13:13" --until "2020-08-06 13:13:13" smartbus #查看某时间段的日志⑥、docker logs -f -t --since="2020-08-01" smartbus | grep error >>logs_error.txt #将错误日志写入文件
```

6、进入容器

```
docker exec -it [容器id] /bin/bash
```

从docker容器进入镜像容器后台例如进行mysql容器,例如：docker exec -it b30062adc08c /bin/bash 这样子就可以操作mysql容器

7、查看docker正在运行的容器

```
docker ps
```

![9e89323794a8b5109c3ec8d9284ee76d.png](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/9e89323794a8b5109c3ec8d9284ee76d.png)

8、停止容器

```
docker stop 
```

9、重启容器

```
docker restart 
```

10、拉取远程镜像

```
docker pull 镜像名<:tags># 从远程仓库抽取镜像,<:tags>是指镜像的版本,不加就是下载最新的镜像 例如：docker pull tomcat:7
```

11、创建容器，并且启动容器

```
docker run 镜像名<:tags> #如果不需要启动容器的话，直接用docker create 镜像名<:tags>
```

12、删除指定容器

```
docker rm  容器id#如果这个容器还在运行的情况下，加上-f这个参数代表强制删除
```

13、删除指定版本的镜像

```
docker rmi  镜像名:#加-f就是强制删除，即使这个镜像有对应的容器
```

14、查看所有的镜像和容器存储在宿主机的哪个位置 默认是存储在这个地址 cd /var/lib/docker

![0a3a5abbef058d5d4259a30922fe4693.png](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/0a3a5abbef058d5d4259a30922fe4693.png)

15、删除docker所有容器

```
docker rm $(docker ps -aq)
```

![c7fd62c92e74d54f23d8d7b2b25e1d46.png](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/c7fd62c92e74d54f23d8d7b2b25e1d46.png)

## Docker 安装 MySQL



MySQL 是世界上最受欢迎的开源数据库。凭借其可靠性、易用性和性能，MySQL 已成为 Web 应用程序的数据库优先选择。

### 1、查看可用的 MySQL 版本

访问 MySQL 镜像库地址：https://hub.docker.com/_/mysql?tab=tags 。

可以通过 Sort by 查看其他版本的 MySQL，默认是最新版本 **mysql:latest** 。

[![img](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/docker-mysql1.png)

你也可以在下拉列表中找到其他你想要的版本：

[![img](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/docker-mysql2.png)](https://www.runoob.com/wp-content/uploads/2016/06/docker-mysql2.png)

此外，我们还可以用 **docker search mysql** 命令来查看可用版本：

```
$ docker search mysql
NAME                     DESCRIPTION                                     STARS     OFFICIAL   AUTOMATED
mysql                    MySQL is a widely used, open-source relati...   2529      [OK]       
mysql/mysql-server       Optimized MySQL Server Docker images. Crea...   161                  [OK]
centurylink/mysql        Image containing mysql. Optimized to be li...   45                   [OK]
sameersbn/mysql                                                          36                   [OK]
google/mysql             MySQL server for Google Compute Engine          16                   [OK]
appcontainers/mysql      Centos/Debian Based Customizable MySQL Con...   8                    [OK]
marvambass/mysql         MySQL Server based on Ubuntu 14.04              6                    [OK]
drupaldocker/mysql       MySQL for Drupal                                2                    [OK]
azukiapp/mysql           Docker image to run MySQL by Azuki - http:...   2                    [OK]
...
```

### 2、拉取 MySQL 镜像

这里我们拉取官方的最新版本的镜像：

```
$ docker pull mysql:latest
```

[![img](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/docker-mysql3.png)](https://www.runoob.com/wp-content/uploads/2016/06/docker-mysql3.png)

### 3、查看本地镜像

使用以下命令来查看是否已安装了 mysql：

```
$ docker images
```

[![img](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/docker-mysql6.png)](https://www.runoob.com/wp-content/uploads/2016/06/docker-mysql6.png)

在上图中可以看到我们已经安装了最新版本（latest）的 mysql 镜像。

### 4、运行容器

安装完成后，我们可以使用以下命令来运行 mysql 容器：

```
$ docker run -itd --name mysql-test -p 3306:3306 -e MYSQL_ROOT_PASSWORD=123456 mysql
```

参数说明：

- **-p 3306:3306** ：映射容器服务的 3306 端口到宿主机的 3306 端口，外部主机可以直接通过 **宿主机ip:3306** 访问到 MySQL 的服务。
- **MYSQL_ROOT_PASSWORD=123456**：设置 MySQL 服务 root 用户的密码。

[![img](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/docker-mysql4.png)](https://www.runoob.com/wp-content/uploads/2016/06/docker-mysql4.png)

### 5、安装成功

通过 **docker ps** 命令查看是否安装成功：

[![img](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/docker-mysql5.png)](https://www.runoob.com/wp-content/uploads/2016/06/docker-mysql5.png)

本机可以通过 root 和密码 123456 访问 MySQL 服务。

[![img](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/docker-mysql7.png)](https://www.runoob.com/wp-content/uploads/2016/06/docker-mysql7.png)

### **问题**

#### 一、无法连接到 docker hub

```
docker: error pulling image configuration: Get https://registry-1.docker.io/v2/library/mysql/: TLS handshake timeout.
```

##### **解决：**

```
systemctl stop docker

echo "DOCKER_OPTS=\"\$DOCKER_OPTS --registry-mirror=http://f2d6cb40.m.daocloud.io\"" | sudo tee -a /etc/default/docker

service docker restart
```

#### **二、docker加载新的镜像后repository和tag名称都为none**

​	**解决：**

```
docker tag [image id] [name]:[版本]
```

#### **三、删除镜像报错**

```
Error response from daemon: conflict: unable to delete
```

**解决：**

当通过该镜像创建的容器未被销毁时，镜像是无法被删除的。为了验证这一点，我们来做个试验。首先，我们通过 `docker pull alpine` 命令，拉取一个最新的 `alpine` 镜像, 然后启动镜像，让其输出 `hello, docker!`:

![Docker run alpine](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/155271716522566.jpeg)

接下来，我们来删除这个镜像试试：

![Docker 删除镜像](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/155271728646226.jpeg)

可以看到提示信息，无法删除该镜像，因为有容器正在引用他！同时，这段信息还告诉我们，除非通过添加 `-f` 子命令，也就是强制删除，才能移除掉该镜像！

```bash
docker rmi -f docker.io/alpine
```

但是，我们一般不推荐这样暴力的做法，正确的做法应该是：

1. 先删除引用这个镜像的容器；
2. 再删除这个镜像；

也就是，根据上图中提示的，引用该镜像的容器 ID (`9d59e2278553`), 执行删除命令：

```bash
docker rm 9d59e2278553
```

然后，再执行删除镜像的命令：

```bash
docker rmi 5cb3aa00f899
```

![Docker 删除镜像](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/155271780037954.jpeg)

这个时候，就能正常删除了！

#### 四、主机无法连接虚拟机库

```
ERROR 1130: Host X.X.X.X is not allowed to connect to this MySQL serve
```

​		默认服务器直能支持本机用户登录，如果需要用工具链接需要给账号权限才行，具体操作如下

​       创建一个用户，xxxxx是用户名 % 代表任意地址都行123456 是密码

```sql
CREATE USER 'XXXXX'@'%' IDENTIFIED BY '123456';
```

​        授权用户，让他具有所有数据库的操作权限

```sql
grant all privileges on *.* to 'XXXXX'@'%';
```

​		授权用户，让他对所有的数据库具有SUPER 的权限

```sql
grant SUPER on *.* to 'XXXXX'@'%';
```

​		刷新权限

```sql
flush privileges;
```

​        这样在链接就好了，

​		如果root用户还不行

​		![image-20210927084510250](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/image-20210927084510250.png)

将Host改为%，代表所有IP可连接

改完刷新权限

#### **五、MySQL 5.7root用户密码修改**

在MySQL 5.7 password字段已从mysql.user表中删除，新的字段名是“authenticalion_string”。

选择数据库

```sql
use mysql;
```

更新root的密码：

```sql
update user set authentication_string=password('新密码') where user='root' and Host='localhost';
```

刷新权限：

```sql
flush privileges;
```













# Oracle 笔记

## 一、常用语句

### 1、查询锁表

```sql
select t2.username,
       t2.sid,
       t2.serial#,
       t3.object_name,
       t2.OSUSER,
       t2.MACHINE,
       t2.PROGRAM,
       t2.LOGON_TIME,
       t2.COMMAND,
       t2.LOCKWAIT,
       t2.SADDR,
       t2.PADDR,
       t2.TADDR,
       t2.SQL_ADDRESS,
       t1.LOCKED_MODE
  from v$locked_object t1, v$session t2, dba_objects t3
 where t1.session_id = t2.sid
   and t1.object_id = t3.object_id
 order by t2.logon_time;
```

### 2、解决锁表

```sql
alter system kill session 'sid,seial#';
```

### 3、创建表空间

```sql
create tablespace TEST_DATA 
logging 
datafile 'E:\oracle\oradata\orcl\TEST_DATA.dbf' 
size 50m 
autoextend on 
next 50m maxsize UNLIMITED 
extent management local; 
```

### 4、创建临时表空间

```sql
create temporary tablespace TEST_TEMP
tempfile 'E:\oracle\oradata\orcl\TEST_TEMP.dbf' 
size 50m 
autoextend on 
next 50m maxsize UNLIMITED 
extent management local;
```

### 5、创建用户

```sql
create user test_username identified by 123456 
default tablespace TEST_DATA 
temporary tablespace TEST_TEMP; 
```

### 6、分配权限

```sql
grant connect,resource,dba to test_username; 
```

### 7、查询当前用户下某些字段在那个表

```sql
select table_name,column_name from user_tab_columns where column_name like '%column_name %';  
```

### 8、回滚误操作

```sql
select * from 表名 as of timestamp to_timestamp('2017-7-24 17:35:50','yyyy-mm-dd hh24:mi:ss');
```

### 9、修改用户名

```sql
 UPDATE USER$ SET NAME='JXZJXT1231SIT' WHERE user#=ZXZJXT1231SIT;
     COMMIT;
```

### 10、Expdp Impdp 数据泵导入导出

**导出** 

```sql
sql>conn username/password@orcl as sysdba;
sql>create directory dmp_dir as 'd:\temp';
sql>select * from dba_directories;

sql>grant read,write on directory dmp_dir to username;

sql>grant exp_full_database to username;
sql>grant imp_full_database to username;

sql>alter user username quota unlimited on user_tablespace ; 

c:\expdp username/password@ip/orcl DIRECTORY=dmp_dir SCHEMAS=schema_name(username) dumpfile=XXX.dmp logfile=XXX.log 

-- content=metadata_only : 表结构
-- include=TABLE,VIEW,Procedure,sequence (表、视图、存储过程、序列)
c:\expdp username/password@ip/orcl DIRECTORY=dmp_dir SCHEMAS=schema_name(username) dumpfile=XXX.dmp logfile=XXX.log CONTENT=METADATA_ONLY INCLUDE=TABLE,VIEW,Procedure,sequence
```

高版本兼容低版本

```sql
expdp system/oracle@ip:1521/dbname directory=dmp11g logfile=xxx.log dumpfile=xxx_%U.dmp parallel=8 schemas=user1,user2 compression=all version=11.2.0.0.0 cluster=n

impdp system/oracle directory=dmp11g logfile=xxx.09011.log dumpfile=xxx_%U.dmp parallel=8 schemas=user1,user2 cluster=n
```



新建逻辑目录，Oracle不会自动创建实际的物理目录“D:\temp”（务必先手动创建此目录然后再执行oracle 导出目录定义），仅仅是进行定义逻辑路径dmp_dir；  

```bash
sql>conn username/password@orcl as sysdba;
sql>create directory dmp_dir as 'd:\temp';
sql>select * from dba_directories;
```

oracle 定义路径前必须创建物理地址，不然会出现如下错误。  

```sql
    ORA-39002: invalid operation
    ORA-39070: Unable to open the log file.
    ORA-29283: invalid file operation
    ORA-06512: at "SYS.UTL_FILE", line 536
    ORA-29283: invalid file operation
```

确认目录存在，当出现如下错误，看看是否有授权 

```sql
ORA-39002: invalid operation
ORA-39070: Unable to open the log file.
ORA-39087: directory name DUMP_DIR is invalid
```

解决方法：

```sql
grant read,write on directory dump_dir to username;
```

导出时出现如下错误，表示没有给用户授权（grant exp_full_database to username;）

```sql
    ORA-31631: privileges are required

    ORA-39161: Full database jobs require privileges
```

导入时出现如下错误，表示没有给用户授权（grant imp_full_database to username;）

```sql
    ORA-31631: privileges are required

    ORA-39122: Unprivileged users may not perform REMAP_SCHEMA remappings.
```

表空间已满提示错误：

```sql
    ORA-31626: job does not exist
    ORA-31633: unable to create master table "DRM_PFM.SYS_EXPORT_FULL_06"
    ORA-06512: at "SYS.DBMS_SYS_ERROR", line 95
    ORA-06512: at "SYS.KUPV$FT", line 1020
    ORA-01658: unable to create INITIAL extent for segment in tablespace TS_PFM
```

查看表空间情况：

```sql
SELECT a.tablespace_name "表空间名",
       total / 1024 / 1024 "表空间大小单位[M]",
       free / 1024 / 1024 "表空间剩余大小单位[M]",
       (total - free) / 1024 / 1024 "表空间使用大小单位[M]",
       Round((total - free) / total, 4) * 100 "使用率   [%]"
  FROM (SELECT tablespace_name, Sum(bytes) free
          FROM DBA_FREE_SPACE
         GROUP BY tablespace_name) a,
       (SELECT tablespace_name, Sum(bytes) total
          FROM DBA_DATA_FILES
         GROUP BY tablespace_name) b
 WHERE a.tablespace_name = b.tablespace_name;
```

解决方法：

```
-- 增加表空间容量
ALTER DATABASE DATAFILE 'D:\DEVELOP\DATABASE\TABLESPACE\TS_PFM.DBF' RESIZE 200M;

-- 修改表空间自动扩展
ALTER DATABASE DATAFILE 'D:\DEVELOP\DATABASE\TABLESPACE\TS_PFM.DBF' AUTOEXTEND ON NEXT 100M MAXSIZE 1G;
```

​    如果表空间设置了自动扩展，查询到的表空间容量快满了，手动执行表空间容量增加；我的就是设置了表空间自动扩展的，但是expdp 导出的时候还是报错，通过手动增加容量解决问题。  

文件已存在提示错误，删除之前因为出现错误创建的文件重新执行即可。

```sql
    ORA-39001: invalid argument value
    ORA-39000: bad dump file specification
    ORA-31641: unable to create dump file "d:\temp\oracle\drm_pfm0711.dmp"
    ORA-27038: created file already exists
    OSD-04010: <create> option specified, file already exists
```

根据用户导出数据提示

```sql
ORA-31626: job does not exist
ORA-31633: unable to create master table "DRM_PFM.SYS_EXPORT_SCHEMA_05"
ORA-06512: at "SYS.DBMS_SYS_ERROR", line 95
ORA-06512: at "SYS.KUPV$FT", line 1020
ORA-01950: no privileges on tablespace 'TS_PFM'
```

解决办法

```sql
SQL> alter user jnzjxt quota unlimited on tablespace_name ; 
```

 

**导入**

```sql
Impdp jnzjxt/jnzjxt@orcl directory=dmp_dir dumpfile=jnzjxt_expdp.dmp logfile=jnzjxt_impdp.log schemas=jnzjxt table_exists_action=append
```



角色确实不存在忽略即可，如果还是导入不了看看是否是表空间不足。

```sql
IMP-00058: ORACLE error 1653 encountered
ORA-01653: unable to extend table user.testTable by 8 in tablespace TS_test
IMP-00028: partial import of previous table rolled back: 10 rows rolled back
IMP-00017: following statement failed with ORACLE error 1917: 
           "GRANT SELECT ON "testTable" TO "testUser""
IMP-00003: ORACLE error 1917 encountered
ORA-01917: user or role 'testUser' does not exist
```

 

```sql
ORA-39006: internal error
ORA-39213: Metadata processing is notavailable
SQL> execute  sys.dbms_metadata_util.load_stylesheets;
```

 

## 二、错误代码

### 1、ORA-00001

```
违反唯一约束条件
```

### 2、Impdp 导入报错

```
高版本向低版本导入必须加版本号
dmp文件放到创建的directory=dmp_dir 路径下
```

### 3、ORA-01940 无法删除当前已连接的用户

首先查询一下数据中有没有用户在使用

```
select username,sid,serial#,paddr from v$session where username='ECITY';
USERNAME                                    SID    SERIAL# PADDR
------------------------------ ---------- -------------------------------------------------
ECITY                                       634        7   00000000C028D198
SQL> select PROGRAM from v$process where addr='00000000C028D198';
PROGRAM
----------------------------------------------------------------------------------------------------------
Oracle@oradb01 (DW00)
```

其次杀掉系统中的这个进程

```
SQL> alter system kill session '634,7';
System altered.
```

然后执行删除操作，即可完成

```
SQL> select saddr,sid,serial#,paddr,username,status from v$session where username is not null;
SQL> drop user ecity CASCADE;
User dropped.
```

问题解决，记得KILL进程前，先看看是啥进程，哪台机连过来的，能否KILL等等。避免杀掉其他进程





























# Extjs 笔记

## 一、字段注释

### 1、 region

页面布局：主要使用一个控件panel，感觉就相当于HTML中的div。位置通过region来设置。

有一点需要注意的是，使用region来布局，位置一定要设成north→center→south或者west→center→east。如果只有两块就west→center而不能westr→east。 

```
region: 'west',//自动排位置
```

### 2、显示边界

```js
style:'border:1px solid #3399ff;',
```

### 3、表格自动产生序号

```js
new Ext.grid.RowNumberer({width:30}),
```





























# Node.js 笔记





![nodejs](https://aixz-imges.oss-cn-beijing.aliyuncs.com/typora_imges/nodejs.jpg)

简单的说 Node.js 就是运行在服务端的 JavaScript。

Node.js 是一个基于Chrome JavaScript 运行时建立的一个平台。

Node.js是一个事件驱动I/O服务端JavaScript环境，基于Google的V8引擎，V8引擎执行Javascript的速度非常快，性能非常好。





## NPM 使用介绍



NPM是随同NodeJS一起安装的包管理工具，能解决NodeJS代码部署上的很多问题，常见的使用场景有以下几种：

- 允许用户从NPM服务器下载别人编写的第三方包到本地使用。
- 允许用户从NPM服务器下载并安装别人编写的命令行程序到本地使用。
- 允许用户将自己编写的包或命令行程序上传到NPM服务器供别人使用。

由于新版的nodejs已经集成了npm，所以之前npm也一并安装好了。同样可以通过输入 **"npm -v"** 来测试是否成功安装。命令如下，出现版本提示表示安装成功:

```
$ npm -v
2.3.0
```

如果你安装的是旧版本的 npm，可以很容易得通过 npm 命令来升级，命令如下：

```
$ sudo npm install npm -g
/usr/local/bin/npm -> /usr/local/lib/node_modules/npm/bin/npm-cli.js
npm@2.14.2 /usr/local/lib/node_modules/npm
```

如果是 Window 系统使用以下命令即可：

```
npm install npm -g
```

> 使用淘宝镜像的命令：
>
> ```
> npm install -g cnpm --registry=https://registry.npm.taobao.org
> ```

------

### 使用 npm 命令安装模块

npm 安装 Node.js 模块语法格式如下：

```
$ npm install <Module Name>
```

以下实例，我们使用 npm 命令安装常用的 Node.js web框架模块 **express**:

```
$ npm install express
```

安装好之后，express 包就放在了工程目录下的 node_modules 目录中，因此在代码中只需要通过 **require('express')** 的方式就好，无需指定第三方包路径。

```
var express = require('express');
```

------

### 全局安装与本地安装

npm 的包安装分为本地安装（local）、全局安装（global）两种，从敲的命令行来看，差别只是有没有-g而已，比如

```
npm install express          # 本地安装
npm install express -g   # 全局安装
```

如果出现以下错误：

```
npm err! Error: connect ECONNREFUSED 127.0.0.1:8087 
```

解决办法为：

```
$ npm config set proxy null
```

#### 本地安装

- \1. 将安装包放在 ./node_modules 下（运行 npm 命令时所在的目录），如果没有 node_modules 目录，会在当前执行 npm 命令的目录下生成 node_modules 目录。
- \2. 可以通过 require() 来引入本地安装的包。

#### 全局安装

- \1. 将安装包放在 /usr/local 下或者你 node 的安装目录。
- \2. 可以直接在命令行里使用。

如果你希望具备两者功能，则需要在两个地方安装它或使用 **npm link**。

接下来我们使用全局方式安装 express

```
$ npm install express -g
```

安装过程输出如下内容，第一行输出了模块的版本号及安装位置。



## Nodejs 服务后台常驻



### 一、利用 forever



forever是一个nodejs守护进程，完全由命令行操控。forever会监控nodejs服务，并在服务挂掉后进行重启。

1、安装 forever

```shell
npm install forever -g
```

2、启动服务

```shell
service forever start
```

3、使用 forever 启动 js 文件

```shell
forever start index.js
```

4、停止 js 文件

```shell
forever stop index.js
```

5、启动js文件并输出日志文件

```shell
forever start -l forever.log -o out.log -e err.log index.js
```

6、重启js文件

```shell
forever restart index.js
```

7、查看正在运行的进程

```shell
forever list
```



### 二、PM2



pm2是一个进程管理工具,可以用它来管理你的node进程,并查看node进程的状态,当然也支持性能监控,进程守护,负载均衡等功能

```shell
npm install -g pm2
pm2 start app.js        // 启动
pm2 start app.js -i max //启动 使用所有CPU核心的集群
pm2 stop app.js         // 停止
pm2 stop all            // 停止所有
pm2 restart app.js      // 重启
pm2 restart all         // 重启所有
pm2 delete  app.js      // 关闭
```

### 三、nohub



nodejs 自带node.js自带服务nohub，不需要安装别的包。
缺点：存在无法查询日志等问题,关闭终端后服务也就关闭了， 经测试是这样的。

```shell
nohup node ***.js &
```







## 问题



























# 开发工具笔记



## 一、IDEA 快捷键

```
Ctrl+Z：撤销

Ctrl+Shift+Z：重做

Ctrl+X：剪贴

Ctrl+C：复制

Ctrl+V：粘贴

Ctrl+Y：删除当前行

Ctrl+D:复制当前行

Ctrl+Shift+J：将选中的行合并成一行

Ctrl+N：查找类文件

Ctrl+Shift+N：查找文件

Ctrl+G：定位到文件某一行

Alt+向左箭头：返回上次光标位置

Alt+向右箭头：返回至后一次光标位置

Ctrl+Shift+Backspace：返回上次编辑位置

Ctrl+Shift+反斜杠：返回后一次编辑位置

Ctrl+B：定位至变量定义的位置

Ctrl+Alt+B：定位至选中类或者方法的具体实现

Ctrl+Shift+B:直接定位至光标所在变量的类型定义

Ctrl+U：直接定位至当前方法override或者implements的方法定义处

Ctrl+F12：显示当前文件的文件结构

Ctrl+Alt+F12：显示当前文件的路径，并可以方便的将相关父路径打开

Ctrl+H：显示当前类的继承层次

Ctrl+Shift+H：显示当前方法的继承层次

Ctrl+Alt+H：显示当前方法的调用层次

F2：定位至下一个错误处

Shift+F2：定位至前一个错误处

Ctrl+Alt+向上箭头：查找前一个变量共现的地方

Ctrl+Alt+向下箭头：查找下一个变量共现的地方

Ctrl+=：展开代码

Ctrl+-：收缩代码

Ctrl+Alt+=：递归展开代码

Ctrl+Alt+-：递归收缩代码

Ctrl+Shift+=：展开所有代码

Ctrl+Shift+-：收缩所有代码

Ctrl+Shitft+向下箭头：将光标所在的代码块向下整体移动

Ctrl+Shift+向上箭头：将光标所在的代码块向上整体移动

Ctrl+Alt+Shift+向左箭头：将元素向左移动

Ctrl+Alt+Shift+向右箭头：将元素向右移动

Alt+Shift+向下箭头：将行向下移动

Alt+Shift+向上箭头：将行向上移动

Ctrl+F：在当前文件中查找

Ctrl+R：替换字符串

Ctrl+Shift+F:在全局文件中查找字符串

Ctrl+Shift+R：在全局中替换字符串

Alt+F7：查找当前变量的使用，并列表显示

Ctrl+Alt+F7：查找当前变量的使用，并直接对话框提示

Ctrl+F7：在文件中查找符号的使用

Ctrl+Shift+F7：在文件中高亮显示变量的使用

Ctrl+O：重写基类方法

Ctrl+I：实现基类或接口中的方法

Alt+Insert：产生构造方法，get/set方法等

Ctrl+Alt+T：将选中的代码使用if，while，try/catch等包装

Ctrl+Shitf+Delete：去除相关的包装代码

Alt+/：自动完成

Alt+Enter：自动提示完成，抛出异常

Ctrl+J：插入Live Template 快速插入一行或者多行代码

Ctrl+Alt+J：使用Live Template包装

Ctrl+/：使用//注释

Ctrl+Shift+/：使用/**/注释

Ctrl+Alt+L：格式化代码

Ctrl+Alt+I：自动缩进行

Ctrl+Alt+O：优化import

Ctrl+]：快速跳转至诸如{}围起来的代码块的结尾处

Ctrl+[：快速跳转至诸如{}围起来的代码块的开头处

Ctrl+Shift+Enter：将输入的if，for，函数等等补上{}或者；使代码语句完整

Shift+Enter：在当前行的下方开始新行

Ctrl+Alt+Enter：在当前行的上方插入新行

Ctrl+Delete：删除光标所在至单词结尾处的所有字符

Ctrl+Backspace：删除光标所在至单词开头处的所有字符

Ctrl+向左箭头：将光标移至前一个单词

Ctrl+向右箭头：将光标移至后一个单词

Ctrl+向上箭头：向上滚动一行

Ctrl+向下箭头：向下滚动一行

Ctrl+W：选中整个单词

Ctrl+Shift+U：切换大小写

Shift+F6：重命名

Ctrl+F6：更改函数签名

Ctrl+Shift+F6：更改类型
```







