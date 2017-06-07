### 关闭 SELinux 、PackageKit 并检查umask值

1. 每台节点都必须关掉

   ```
   setenforce 0
   ```

   | 彻底关闭 SELinux，在`/etc/selinux/config 中设置`SELINUX=disabledThis ensures that SELinux does not turn itself on after you reboot the machine . |
   | :--- |

1. 1. On an installation host running RHEL/CentOS with PackageKit installed, open`/etc/yum/pluginconf.d/refresh-packagekit.conf`using a text editor. Make the following change:

   ```
   enabled=0
   ```

   | ![](https://docs.hortonworks.com/HDPDocuments/Ambari-2.5.0.3/bk_ambari-installation/common/images/admon/note.png "\[Note\]") | Note |
   | :--- | :--- |
   |  | PackageKit is not enabled by default on Debian, SLES, or Ubuntu systems. Unless you have specifically enabled PackageKit, you may skip this step for a Debian, SLES, or Ubuntu installation host. |

1. UMASK \(User Mask or User file creation MASK\) sets the default permissions or base permissions granted when a new file or folder is created on a Linux machine. Most Linux distros set 022 as the default umask value. A umask value of 022 grants read, write, execute permissions of 755 for new files or folders. A umask value of 027 grants read, write, execute permissions of 750 for new files or folders.

   Ambari & support umask values of 022 \(0022 is functionally equivalent\), 027 \(0027 is functionally equivalent\). These values must be set on all hosts.

   **UMASK Examples**:

   Setting the umask for your current login session:

   ```
   umask 0022
   ```

   Checking your current umask:

   ```
   umask 0022
   ```

   Permanently changing the umask for all interactive users:

   ```
   echo umask 0022 
   >
   >
    /etc/profile
   ```



