检查本地yum

```
yum repolist
```

检查结果如图，有ambari的repo出现了！

![](/assets/b2.png)

安装ambari-server

```
yum install -y ambari-server
```

设置ambari-server

```
ambari-server setup
```

首先要选择java版本，如果本机已经装过jdk8，选择自定义，然后输入路径。然后还要选择数据库，这里直接用默认的postgresql，安装过程会自动安装，并设置。

