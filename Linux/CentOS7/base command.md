# 查看当前系统的所有用户信息
cat /etc/passwd | grep -v -e '/sbin/nologin' -e '/sbin/halt' -e '/bin/sync' -e '/sbin/shutdown' | awk -F: '{print $1}'


# 查看,开启,关闭,设置开机自启服务

```bash
#列出所有已安装的服务
systemctl list-unit-files

#列出所有正在运行的服务
systemctl list-units

#启动服务 
systemctl start service-name 

#停止服务 
systemctl stop service-name 

#重启服务
systemctl restart service-name 

#查看指定服务的状态
systemctl status service-name 

#开机自启动服务 
systemctl enable service-name 

#禁止开机自启动服务
systemctl disable service-name 
```



# 安装卸载相关

```bash
#查看原有的yum 
rpm -qa | grep yum

#安装服务
yum install -y service-name

#卸载服务
yum remove service-name
```

















































