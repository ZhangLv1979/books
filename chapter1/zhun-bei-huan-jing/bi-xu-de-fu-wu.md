安装服务

**RHEL/CentOS/Oracle 6**

```
yum install -y ntp
```

**RHEL/CentOS/Oracle 7**

```
yum install -y ntp
```

检查服务

**RHEL/CentOS/Oracle 6**

```
chkconfig --list ntpd
```

**RHEL/CentOS/Oracle 7**

```
systemctl is-enabled ntpd
```

设置开机启动

**RHEL/CentOS/Oracle 6**

```
chkconfig ntpd on
```

**RHEL/CentOS/Oracle 7**

```
systemctl enable ntpd
```

To start the NTP service, run the following command on each host:

**RHEL/CentOS/Oracle 6**

```
service ntpd start
```

**RHEL/CentOS/Oracle 7**

```
systemctl start ntpd
```



