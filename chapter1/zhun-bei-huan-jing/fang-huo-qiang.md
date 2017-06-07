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

You can restart iptables after setup is complete. If the security protocols in your environment prevent disabling iptables, you can proceed with iptables enabled, if all required ports are open and available.

Ambari checks whether iptables is running during the Ambari Server setup process. If iptables is running, a warning displays, reminding you to check that required ports are open and available. The Host Confirm step in the Cluster Install Wizard also issues a warning for each host that has iptables running.

