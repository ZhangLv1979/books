### 关闭 SELinux 、PackageKit 并检查umask值

1. 每台节点都必须关掉

   ```
   setenforce 0
   ```

   | 彻底关闭 SELinux，在`/etc/selinux/config 中设置`SELINUX=disabled。 |
   | :--- |

2. 修改`/etc/yum/pluginconf.d/refresh-packagekit.conf`using a text editor. Make the following change:

   ```
   enabled=0
   ```

3. UMASK设置成0022

   **UMASK Examples**:  
   设置

   ```
   umask 0022
   ```

   检查

   ```
   umask 0022
   ```

   永久设置umask值

   ```
   echo umask 0022 >> /etc/profile
   ```



