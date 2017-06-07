## 登录服务器

打开浏览器访问

```
http://<your.ambari.server>:8080
```

默认用户名:密码是admin:admin

![](/assets/c1.png)

点击Launch Install Wizard开始安装

输入集群名称

版本选择你选择的版本，如果没有你的精确的版本号，就选择大版本号，比如2.6.0.1没有，就选2.6.。

安装选项，先输入你的集群的主机名，每行一个，也可以使用通配符，例如s\[1-10\].bishop.com表示s1.bishop.com到s10.bishop.com。然后在ssh key里面上传你在准备阶段准备的密码文件，id\_rsa这个文件，如果你要手动每个节点装agent，就选手动。

