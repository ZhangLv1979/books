### **Ambari 2.5.0 服务器操作系统支持**

| Operating System | Version |
| :--- | :--- |
| CentOS \(64-bit\) | CentOS v7.x |
|  | CentOS v6.x |
| Debian | Debian v7.x |
| Oracle \(64-bit\) | Oracle Linux v7.x |
|  | Oracle Linux v6.x |
| Red Hat \(64-bit\) | RHEL 7.0, 7.1, 7.2 |
|  | RHEL 6.1, 6.2, 6.3, 6.4, 6.5, 6.6, 6.7, 6.8 |
| SUSE \(64-bit\) | \(SLES\) Enterprise Linux 12, SP2 for Teradata |
|  | \(SLES\) Enterprise Linux 12, SP1 |
|  | \(SLES\) Enterprise Linux 11, SP4 \(HDP 2.2 and later\) |
|  | \(SLES\) Enterprise Linux 11, SP3 for Teradata \(HDP 2.2 and later\) |
|  | \(SLES\) Enterprise Linux 11, SP1 \(HDP 2.2\) |
| Ubuntu \(64-bit\) | Ubuntu 16.04 \(Xenial\) |
|  | Ubuntu 14.04 \(Trusty\) |

### **Ambari 2.5.0 浏览器支持**

| Operating System | Browser |
| :--- | :--- |
| Linux | Chrome 56.0.2924.87, 57.0.2987 |
|  | Firefox 51, 52 |
| Mac OS X | Chrome 56.0.2924.87, 57.0.2987 |
|  | Firefox 51, 52 |
|  | Safari 10.0.1, 10.0.3 |
| Windows | Chrome 56.0.2924.87, 57.0.2987 |
|  | Edge 38 |
|  | Firefox 51.0.1, 52.0 |
|  | Internet Explorer 10, 11 |

### 软件环境

在你的集群中，每台主机上都要安装:

* `yum`and`rpm`\(RHEL/CentOS/Oracle Linux\)

* `zypper`and`php_curl`\(SLES\)

* `apt`\(Debian/Ubuntu\)

* `scp, curl, unzip, tar`, and`wget`

* OpenSSL \(v1.01, build 16 or later\)

* Python

  **For SLES 11:**  
  Python 2.6.x

  **For SLES 12:**  
  Python 2.7.x

  **For CentOS 7, Ubuntu 14, Ubuntu 16, and Debian 7:**  
  Python 2.7.x

### **HDP 2.6.0 JDK 支持**

这是最新的HDP大数据平台套件需要的JDK环境，老的版本会有降低。推荐使用JDK8。

| JDK | Version |
| :--- | :--- |
| Open Source | JDK8† |
|  | JDK7†, deprecated |
| Oracle | JDK 8, 64-bit \(minimum JDK 1.8.0\_77\), default |
|  | JDK 7, 64-bit \(minimum JDK 1.7\_67\), deprecated |

### 数据库需求

Ambari安装中可以选择安装数据库，一般来说不必在意本节内容，除非你打算使用自己已有的数据库。

| 组件 | 数据库 | 描述 |
| :--- | :--- | :--- |
| Ambari | PostgreSQL 9.1.13+,9.3, 9.4\*\*\*MariaDB 10\*MySQL 5.6\*\*\*\*Oracle 11gr2Oracle 12c\*\* | 默认安装PostgreSQL，也可以选其他已存在的。 |
| Druid | PostgreSQL 9.1.13+, 9.3, 9.4\*\*\*MariaDB 10\*MySQL 5.6\*\*\*\* |  |
| Hive | PostgreSQL 9.1.13+, 9.3, 9.4\*\*\*MariaDB 10\*MySQL 5.6\*\*\*\*Oracle 11gr2Oracle 12c\*\* | 默认安装MySQL作为Hive的Meta数据库 |
| Oozie | PostgreSQL 9.1.13+, 9.3, 9.4\*\*\*MariaDB 10\*MySQL 5.6\*\*\*\*Oracle 11gr2Oracle 12c\*\* | 默认安装Derby，也可以使用已存在的其他库。 |
| Ranger | PostgreSQL 9.1.13+, 9.3, 9.4\*\*\*MariaDB 10\*MySQL 5.6\*\*\*\*Oracle 11gr2Oracle 12c\*\* | 必须提供一个数据库。 |

### 内存需求

Ambari 主机最少需要 1 GB RAM, 500 MB 空闲的.

运行以下命令检查你的内存

`free -m`

安装Ambari Metrics Service \(AMS\) 需要以下内存和硬盘空间

| **Number of hosts** | **Memory Available** | **Disk Space** |
| :--- | :--- | :--- |
| 1 | 1024 MB | 10 GB |
| 10 | 1024 MB | 20 GB |
| 50 | 2048 MB | 50 GB |
| 100 | 4096 MB | 100 GB |
| 300 | 4096 MB | 100 GB |
| 500 | 8096 MB | 200 GB |
| 1000 | 12288 MB | 200 GB |
| 2000 | 16384 MB | 500 GB |

### 空间占用

|  | **Size** | **Inodes** |
| :--- | :--- | :--- |
| Ambari Server | 100MB | 5,000 |
| Ambari Agent | 8MB | 1,000 |
| Ambari Metrics Collector | 225MB | 4,000 |
| Ambari Metrics Monitor | 1MB | 100 |
| Ambari Metrics Hadoop Sink | 8MB | 100 |
| After Ambari Server Setup | N/A | 4,000 |
| After Ambari Server Start | N/A | 500 |
| After Ambari Agent Start | N/A | 200 |

### 检查最大文件打开数限制

推荐 10000以上。

在每台集群机上运行一下命令检查。

    `ulimit -Sn`

    `ulimit -Hn`

小于10000的运行下面的代码来修改。

`ulimit -n 10000`

