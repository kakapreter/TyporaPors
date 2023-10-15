## 扫描局域网下所有存活的主机

```bash
┌──(root㉿bogon)-[~]
└─# arp-scan -l
Interface: eth0, type: EN10MB, MAC: 00:0c:29:91:cb:e4, IPv4: 192.168.32.163
Starting arp-scan 1.10.0 with 256 hosts (https://github.com/royhills/arp-scan)
192.168.32.1    00:50:56:c0:00:08       VMware, Inc.
192.168.32.2    00:50:56:fc:c1:f7       VMware, Inc.
192.168.32.162  00:0c:29:b3:ae:1a       VMware, Inc.
192.168.32.254  00:50:56:f7:e1:64       VMware, Inc.
```
## 要扫描目标主机的信息，包括操作系统版本、开放端口和服务
```bash
┌──(root㉿bogon)-[~]
└─# nmap -A 192.168.32.162
Starting Nmap 7.94 ( https://nmap.org ) at 2023-10-15 03:42 EDT
Stats: 0:00:11 elapsed; 0 hosts completed (1 up), 1 undergoing Script Scan
NSE Timing: About 97.96% done; ETC: 03:42 (0:00:00 remaining)
Nmap scan report for 192.168.32.162 (192.168.32.162)
Host is up (0.00063s latency).
Not shown: 989 filtered tcp ports (no-response), 10 filtered tcp ports (host-prohibited)
PORT   STATE SERVICE VERSION
22/tcp open  ssh     OpenSSH 7.4 (protocol 2.0)
| ssh-hostkey: 
|   2048 ae:b8:28:14:11:5b:f4:9f:4c:8b:19:e9:2a:ce:7f:66 (RSA)
|   256 66:a7:f2:32:af:76:95:8d:59:07:24:6b:09:9b:6d:bf (ECDSA)
|_  256 7e:2e:bc:08:52:30:0f:4c:47:bd:c5:a5:de:13:6e:5d (ED25519)
MAC Address: 00:0C:29:B3:AE:1A (VMware)
Warning: OSScan results may be unreliable because we could not find at least 1 open and 1 closed port
Device type: general purpose|storage-misc
Running (JUST GUESSING): Linux 3.X|4.X|5.X|2.6.X (97%), Synology DiskStation Manager 5.X (90%), Netgear RAIDiator 4.X (87%)
OS CPE: cpe:/o:linux:linux_kernel:3 cpe:/o:linux:linux_kernel:4 cpe:/o:linux:linux_kernel:5.1 cpe:/o:linux:linux_kernel:2.6.32 cpe:/a:synology:diskstation_manager:5.2 cpe:/o:netgear:raidiator:4.2.28
Aggressive OS guesses: Linux 3.10 - 4.11 (97%), Linux 3.2 - 4.9 (97%), Linux 5.1 (97%), Linux 3.13 - 3.16 (91%), Linux 3.16 - 4.6 (91%), Linux 4.10 (91%), Linux 4.4 (91%), Linux 2.6.32 (91%), Linux 3.4 - 3.10 (91%), Linux 4.15 - 5.8 (91%)
No exact OS matches for host (test conditions non-ideal).
Network Distance: 1 hop

TRACEROUTE
HOP RTT     ADDRESS
1   0.63 ms 192.168.32.162 (192.168.32.162)

OS and Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 14.18 seconds
```
