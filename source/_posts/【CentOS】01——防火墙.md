---
title: 【CentOS】01——防火墙
date: 2017-01-23 13:42:56
tags: [CentOS,iptables,防火墙]
categories: [Linux]
---
- CentOS下通过iptables对防火墙设置的常用操作
<!-- more -->

--------------------------------

1. 查看iptables现有规则
iptables -L -n
2. 先允许所有,不然有可能会杯具
iptables -P INPUT ACCEPT
3. 清空所有默认规则
iptables -F
4. 清空所有自定义规则
iptables -X
5. 所有计数器归0
iptables -Z
6. 允许来自于lo接口的数据包(本地访问)
iptables -A INPUT -i lo -j ACCEPT
7. 开放22端口
iptables -A INPUT -p tcp --dport 22 -j ACCEPT
8. 开放21端口(FTP)
iptables -A INPUT -p tcp --dport 21 -j ACCEPT
9. 开放80端口(HTTP)
iptables -A INPUT -p tcp --dport 80 -j ACCEPT
10. 开放443端口(HTTPS)
iptables -A INPUT -p tcp --dport 443 -j ACCEPT
11. 允许ping
iptables -A INPUT -p icmp --icmp-type 8 -j ACCEPT
12. 允许接受本机请求之后的返回数据 RELATED,是为FTP设置的（？）
iptables -A INPUT -m state --state  RELATED,ESTABLISHED -j ACCEPT
13. 其他入站一律丢弃
iptables -P INPUT DROP
14. 所有出站一律绿灯
iptables -P OUTPUT ACCEPT
15. 所有转发一律丢弃
iptables -P FORWARD DROP

