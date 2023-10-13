# 更换yum源

> 由于CentOS7默认的yum源是国外的，导致我们使用yum下载软件的下载速度不是很理想，这时候我们就需要将yum源更换成国内的源。

## 首先我们先对系统本身的yum源进行备份

```bash
 mv /etc/yum.repos.d/CentOS-Base.repo /etc/yum.repos.d/CentOS-Base.repo.backup
```

> 这条命令用于将/etc/yum.repos.d/CentOS-Base.repo文件重命名为/etc/yum.repos.d/CentOS-Base.repo.backup。

> 在Linux系统中，mv命令用于移动文件或重命名文件。在这个命令中，/etc/yum.repos.d/CentOS-Base.repo是要移动或重命名的原始文件路径，/etc/yum.repos.d/CentOS-Base.repo.backup是目标文件路径。

> 执行该命令后，CentOS-Base.repo文件将被重命名为CentOS-Base.repo.backup，并放置在相同的目录中。这样做可以为CentOS-Base.repo文件创建一个备份，以免不小心修改或删除该文件时丢失重要的配置。

## 下载国内yum源配置文件到/etc/yum.repos.d/CentOS-Base.repo

```bash
阿里云 CentOS 7 源（推荐）：
wget -O /etc/yum.repos.d/CentOS-Base.repo http://mirrors.aliyun.com/repo/Centos-7.repo

网易163 CentOS 7 源：
wget -O /etc/yum.repos.d/CentOS-Base.repo http://mirrors.163.com/.help/CentOS7-Base-163.repo

搜狐 CentOS 7 源：
wget -O /etc/yum.repos.d/CentOS-Base.repo http://mirrors.sohu.com/help/CentOS7-Base-sohu.repo

华为云 CentOS 7 源：
wget -O /etc/yum.repos.d/CentOS-Base.repo http://mirrors.myhuaweicloud.com/repo/CentOS-7.repo

华东理工大学 CentOS 7 源：
wget -O /etc/yum.repos.d/CentOS-Base.repo https://mirrors.ustc.edu.cn/centos/7/os/x86_64

清华大学 CentOS 7 源：
wget -O /etc/yum.repos.d/CentOS-Base.repo https://mirrors.tuna.tsinghua.edu.cn/centos/7/os/x86_64/

北京理工大学 CentOS 7 源：
wget -O /etc/yum.repos.d/CentOS-Base.repo https://mirrors.bfsu.edu.cn/centos/7/os/x86_64/

上海交通大学 CentOS 7 源：
wget -O /etc/yum.repos.d/CentOS-Base.repo https://ftp.sjtu.edu.cn/centos/7/os/x86_64/

中国科学技术大学 CentOS 7 源：
wget -O /etc/yum.repos.d/CentOS-Base.repo https://mirrors.ustc.edu.cn/centos/7/os/x86_64/

兰州大学 CentOS 7 源：
wget -O /etc/yum.repos.d/CentOS-Base.repo https://mirror.lzu.edu.cn/centos/7/os/x86_64/
以上命令选择一个就行了 
```

## 清理yum缓存

```bash
yum clean all
```
## 生成新的缓存
```bash
yum makecache
```
## 更新yum源检查是否生效

```bash
yum update -y
```

