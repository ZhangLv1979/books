安装时集群内部最好关掉防火墙，关掉每台节点上的防火墙

**RHEL/CentOS/Oracle Linux 6**

```
chkconfig iptables off
```

```
/etc/init.d/iptables stop
```

**RHEL/CentOS/Oracle Linux 7**

```
systemctl disable firewalld
```

```
service firewalld stop
```



