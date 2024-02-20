# vi /etc/sysconfig/network-scripts/ifcfg-ens33

TYPE=Ethernet

PROXY_METHOD=none

BROWSER_ONLY=no

BOOTPROTO=static  #dhcp改成static

DEFROUTE=yes

IPV4_FAILURE_FATAL=no

IPV6INIT=yes

IPV6_AUTOCONF=yes

IPV6_DEFROUTE=yes

IPV6_FAILURE_FATAL=no

IPV6_ADDR_GEN_MODE=stable-privacy

NAME=ens33

UUID=796a9160-cd67-4a34-baa9-819e3da1813f   #如果复制虚拟机的话改UUID

DEVICE=ens33

ONBOOT=yes               #no改成yes

IPADDR=192.168.200.100   #添加

NETMASK=255.255.255.0    #添加

GATEWAY=192.168.200.254  #添加

DNS1=8.8.8.8             #添加

DNS2=114.114.114.114     #添加

修改完之后执行
# service network restart

# vi /etc/hostname

# vi /etc/resolv.conf
nameserver 8.8.8.8

nameserver 114.114.114.114

# yum install net-tools
