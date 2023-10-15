## 更新系统版本 & 清理不再需要的依赖软件包 & 清屏
```bash
┌──(root㉿bogon)-[~]
apt update && apt -y full-upgrade && apt autoremove && clear
```

## 更新软件包 & 清理本地存储的已下载包文件 & 清屏
```bash
┌──(root㉿bogon)-[~]
apt-get update && apt-get upgrade && apt-get clean && clear
```

