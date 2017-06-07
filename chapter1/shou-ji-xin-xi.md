开始安装前，让我们先来收集一下信息。

* 全规格的主机名

  ```
  hostname -f
  ```

  to check or verify the FQDN of a host.

  | ![](https://docs.hortonworks.com/HDPDocuments/Ambari-2.5.0.3/bk_ambari-installation/common/images/admon/note.png "\[Note\]") | Note |
  | :--- | :--- |
  |  | Deploying all components on a single host is possible, but is appropriate only for initial evaluation purposes. Typically, you set up at least three hosts; one master host and two slaves, as a minimum cluster. |

* A list of components you want to set up on each host.

* The base directories you want to use as mount points for storing:

  * NameNode data

  * DataNodes data

  * Secondary NameNode data

  * Oozie data

  * YARN data

  * ZooKeeper data, if you install ZooKeeper

  * Various log, pid, and db files, depending on your install type



