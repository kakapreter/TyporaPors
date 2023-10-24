# CentOS7 删除多余内核
## 更新系统和软件
```bash
yum -y update && yum clean all && yum makecache && yum -y upgrade
```
## 查看内核列表

```bash
rpm -qa | grep kernel
```

系统安装的所有内核，如下：

> kernel-tools-3.10.0-1160.53.1.el7.x86_64
> kernel-devel-3.10.0-1160.el7.x86_64
> kernel-tools-libs-3.10.0-1160.53.1.el7.x86_64
> kernel-headers-3.10.0-1160.53.1.el7.x86_64
> kernel-3.10.0-1160.53.1.el7.x86_64
> kernel-3.10.0-1160.el7.x86_64
> kernel-devel-3.10.0-1160.53.1.el7.x86_64
> kernel-devel-3.10.0-1160.42.2.el7.x86_64

## 查看系统当前正在使用内核

```bash
uname -r
```

显示目前使用内核：

> 3.10.0-1160.el7.x86_64

## 删除多余内核

命令：rpm -e 内核名称，（yum remove 命令也可以）比如：

```bash
rpm -e kernel-3.10.0-1160.53.1.el7.x86_64
```

或者使用下面命令删除多余的内核：（以上与以下操作均需确认清楚）

```bash
yum remove kernel-3.10.0-1160.53.1.el7.x86_64
```

## 重新编译引导
```bash
grub2-mkconfig -o /boot/grub2/grub.cfg
```
## 重启系统
```bash
reboot
```
