1. Download the`ambari.repo`file from the public repository.

   ```
   http://public-repo-1.hortonworks.com/ambari/
   <
   OS
   >
   /2.x/updates/2.5.0.3/ambari.repo
   ```

   where &lt;OS&gt; is centos6, centos7, sles11, sles12, ubuntu14, ubuntu16, or debian7.

2. Edit the`ambari.repo`file and replace the Ambari Base URL`baseurl`obtained when setting up your local repository.

   | ![](https://docs.hortonworks.com/HDPDocuments/Ambari-2.5.0.3/bk_ambari-installation/common/images/admon/note.png "\[Note\]") | Note |
   | :--- | :--- |
   |  | You can disable the GPG check by setting gpgcheck =0. Alternatively, you can keep the check enabled but replace the gpgkey with the URL to the GPG-KEY in your local repository. |

   ```
   [Updates-Ambari-2.5.0.3]
   ```

   ```
   name=Ambari-2.5.0.3-Updates
   ```

   ```
   baseurl=INSERT-BASE-URL
   ```

   ```
   gpgcheck=1
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

   **Base URL for a Local Repository**

   **Built with Repository Tarball**  
   \(No Internet Access\)  
   [http://&lt;web.server&gt;/Ambari-2.5.0.3/&lt;OS&gt](http://<web.server>/Ambari-2.5.0.3/<OS&gt);

   **Built with Repository File**  
   \(Temporary Internet Access\)  
   [http://&lt;web.server&gt;/ambari/&lt;OS&gt;/Updates-Ambari-2.5.0.3](http://<web.server>/ambari/<OS>/Updates-Ambari-2.5.0.3)

   where &lt;web.server&gt; = FQDN of the web server host, and &lt;OS&gt; is centos6, centos7, sles11, sles12, , ubuntu14, or debian7.

3. Place the ambari.repo file on the machine you plan to use for the Ambari Server.

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

4. Edit the`/etc/yum/pluginconf.d/priorities.conf`file to add the following:

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

