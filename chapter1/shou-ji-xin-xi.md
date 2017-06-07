开始安装前，让我们先来收集一下信息。

* 全规格的主机名

  ```
  hostname -f
  ```

  没有的话设置所有机器上/etc/hosts  

* 在一个节点上安装全部功能是可以的，但是一般至少3个节点，1主2副。

* A list of components you want to set up on each host.

* The base directories you want to use as mount points for storing:

  * NameNode data

  * DataNodes data

  * Secondary NameNode data

  * Oozie data

  * YARN data

  * ZooKeeper data, if you install ZooKeeper

  * Various log, pid, and db files, depending on your install type



