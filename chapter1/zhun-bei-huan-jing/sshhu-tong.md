Ambari Server 需要在节点机上安装agent，因此需要可以无密码登录ssh的权限来运行脚本。当然也可以手动在每台机上安装agent。

1. 在Ambari服务器上生成公钥.

2. ```
   ssh-keygen
   ```
3. 拷贝公钥到每台节点机上.

   ```
   .ssh/id_rsa
   ```

   ```
   .ssh/id_rsa.pub
   ```

4. 把公钥加入到每台节点机的信任列表中.

   ```
   cat id_rsa.pub 
   >
   >
    authorized_keys
   ```

5. 需要设置目录权限

   ```
   chmod 700 ~/.ssh
   ```

   ```
   chmod 600 ~/.ssh/authorized_keys
   ```

6. From the Ambari Server, make sure you can connect to each host in the cluster using SSH, without having to enter a password.

   ```
   ssh root@
   <
   remote.target.host
   >
   ```

   where`<remote.target.host>`has the value of each host name in your cluster.

7. If the following warning message displays during your first connection:`Are you sure you want to continue connecting (yes/no)?`Enter`Yes`.

8. Retain a copy of the SSH Private Key on the machine from which you will run the web-based Ambari Install Wizard.

   | ![](https://docs.hortonworks.com/HDPDocuments/Ambari-2.5.0.3/bk_ambari-installation/common/images/admon/note.png "\[Note\]") | Note |
   | :--- | :--- |
   |  | It is possible to use a non-root SSH account, if that account can execute`sudo`without entering a password. |



