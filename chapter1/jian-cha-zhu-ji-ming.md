#### 修改网卡设置

1. Using a text editor, open the network configuration file on every host and set the desired network configuration for each host. For example:

   ```
   vi /etc/sysconfig/network
   ```

2. Modify the HOSTNAME property to set the fully qualified domain name.

   ```
   NETWORKING=yes
   ```

   ```
   HOSTNAME=<fully.qualified.domain.name>
   ```



