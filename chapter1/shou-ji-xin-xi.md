Before deploying a cluster, you should collect the following information:

* The fully qualified domain name \(FQDN\) of each host in your system. The Ambari Cluster Install wizard supports using IP addresses. You can use

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



