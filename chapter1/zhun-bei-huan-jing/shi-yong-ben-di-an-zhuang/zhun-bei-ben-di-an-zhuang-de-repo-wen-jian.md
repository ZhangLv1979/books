1. 下载`ambari.repo`.

   ```
   http://public-repo-1.hortonworks.com/ambari/<OS>/2.x/updates/2.5.0.3/ambari.repo
   ```

2. 按照你本地安装的目录修改repo文件.

   ```
   [Updates-Ambari-2.5.0.3]
   ```

   ```
   name=Ambari-2.5.0.3-Updates
   ```

   ```
   baseurl=这里输入ambari的base路径
   ```

   ```
   gpgcheck=0
   ```

   ```
   gpgkey=http://public-repo-1.hortonworks.com/ambari/centos6/RPM-GPG-KEY/RPM-GPG-KEY-Jenkins
   ```

   ```
   enabled=1
   ```

   ```
   priority=1
   ```

3. repo文件复制到yum的repo目录下.

   **For RHEL/CentOS/Oracle Linux:**

   ```
   /etc/yum.repos.d/ambari.repo
   ```

   **For SLES:**

   ```
   /etc/zypp/repos.d/ambari.repo
   ```

   **For Debain/Ubuntu:**

   ```
   /etc/apt/sources.list.d/ambari.list
   ```

4.  修改/`etc/yum/pluginconf.d/priorities.conf`file to add the following:

   ```
   [main]
   ```

   ```
   enabled=1
   ```

   ```
   gpgcheck=0
   ```

**Next Steps**

