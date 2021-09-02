---
xray 用法
---

#xray用法

---

![image-20210824184239877](xray\image-20210824184239877.png)

**###xray文件夹运行命令行**

**###查看帮助**
		命令：xray_windows_amd64.exe -h

**###Xray可借助爬虫进行漏洞检查**
		命令：

​		xray_linux_amd64   webscan --basic-crawler  http://172.16.12.2



windows系统下在xray文件夹下运行cmd，可以将结果输出为html



> ```linux
> xray_windows_amd64.exe webscan --basic-crawler http://192.168.179.75/login/ --html-output 824.html
> ```



**被动扒寻模式**

运行Xray，开启监听,浏览器安装ca证书，设置proxy 开启端口7777

命令：xray_windows_amd64.exe webscan --listen 127.0.0.1:7777 --html-output test.html

现在cmd中开启监听，然后在浏览器 开启代理，刷新网页，进行被动扫描

