Scan Ip In Local Network:
========================================

```
$ nmap -sP 192.168.1.0/24 # 仅列出指定网络上的每台主机，不发送任何报文到目标主机：
$ nmap -sL 192.168.1.0/24 # 探测目标主机开放的端口，可以指定一个以逗号分隔的端口列表
$ nmap -PS 192.168.1.234 # 使用UDP ping探测主机：
$ nmap -PU 192.168.1.0/24 # 使用频率最高的扫描选项: SYN扫描,又称为半开放扫描,它不打开一个完全的TCP连接，执行得很快
$ nmap -sS 192.168.1.0/24 # 当SYN扫描不能用时，TCP Connect()扫描就是默认的TCP扫描：
$ nmap -sT 192.168.1.0/24 # UDP扫描用-sU选项,UDP扫描发送空的(没有数据)UDP报头到每个目标端口:
$ nmap -sU 192.168.1.0/24 # 确定目标机支持哪些IP协议 (TCP，ICMP，IGMP等):
$ nmap -sO 192.168.1.19 # 探测目标主机的操作系统：
$ nmap -O 192.168.1.19
$ nmap -A 192.168.1.19
```
