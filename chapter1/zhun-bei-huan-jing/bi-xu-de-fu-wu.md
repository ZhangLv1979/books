安装ntp服务

**RHEL/CentOS/Oracle 6**

```
yum install -y ntp
```

**RHEL/CentOS/Oracle 7**

```
yum install -y ntp
```

To check that the NTP service will be automatically started upon boot, run the following command on each host:

**RHEL/CentOS/Oracle 6**

```
chkconfig --list ntpd
```

**RHEL/CentOS/Oracle 7**

```
systemctl is-enabled ntpd
```

To set the NTP service to auto-start on boot, run the following command on each host:

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



