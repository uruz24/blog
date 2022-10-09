---
title: centOS6安装
date: 2021-06-08 16:52:17
tags:
---

## 安装centOS6

1.查看ip，进到网卡文件夹

`ip a`   

`cd /etc/sysconfig/network-scripts/`

`ls`

`vi ifcfg-eth0`



2.更改动态IPdhcp为静态static

BOOTRPROTO=dhcp



3.

BOOTRPROTO=static



4.添加静态ip，子网掩码，网关

IPADDR=192.168.24.171

NETMASK=255.255.255.0

GATEWAY=192.168.24.1

:wq保存退出



5.

`if down eth0`  关闭网卡

`ifup eth0`   打开网卡

ip a   查看ip，如果显示，表示静态ip设置成功

`ping 8.8.8.8`   pingGoogle



6.用本机ping虚拟机的静态ip，

`ping 192.168.24.171`



7.连接虚拟机，ip a 显示内容，表示已经连接上虚拟机

本机

`ssh root@192.168.24.171`

`ip a`





\------------------
