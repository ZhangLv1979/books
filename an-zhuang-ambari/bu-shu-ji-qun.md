## 登录服务器

打开浏览器访问

```
http://<your.ambari.server>:8080
```

默认用户名:密码是admin:admin

![](/assets/c1.png)

点击Launch Install Wizard开始安装

输入一个集群名称。

版本选择你选择的版本，我们因为是本地安装的，所以选择local repo，输入对应的baseurl。不需要全输，只需要对应的操作系统就行了。

安装选项这里，先输入你的集群的主机名，每行一个，也可以使用通配符，例如s\[1-10\].bishop.com表示s1.bishop.com到s10.bishop.com。然后在ssh key里面上传你在准备阶段准备的密码文件，id\_rsa这个文件，如果你要手动每个节点装agent，就选手动。

根据你的选择，下一步会安装agent，检查主机的连接情况，如果报错，可以点击信息查看错误信息。

如果能看到你所有的节点，并且都显示成功，恭喜你，后面就没啥问题了。

这里的错误一般发生在ssh没有互信，无法安装agent，或者baseurl不正确导致没法正确的安装agent。解决错误以后retry，直到看到所有的节点都通过。



