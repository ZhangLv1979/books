Ambari Server 需要在节点机上安装agent，因此需要可以无密码登录ssh的权限来运行脚本。当然也可以手动在每台机上安装agent。

1. Generate public and private SSH keys on the Ambari Server host.

1. ```
   ssh-keygen
   ```
2. Copy the SSH Public Key \(id\_rsa.pub\) to the root account on your target hosts.

   ```
   .ssh/id_rsa
   ```

   ```
   .ssh/id_rsa.pub
   ```

3. Add the SSH Public Key to the authorized\_keys file on your target hosts.

   ```
   cat id_rsa.pub 
   >
   >
    authorized_keys
   ```

4. Depending on your version of SSH, you may need to set permissions on the .ssh directory \(to 700\) and the authorized\_keys file in that directory \(to 600\) on the target hosts.

   ```
   chmod 700 ~/.ssh
   ```

   ```
   chmod 600 ~/.ssh/authorized_keys
   ```

5. From the Ambari Server, make sure you can connect to each host in the cluster using SSH, without having to enter a password.

   ```
   ssh root@
   <
   remote.target.host
   >
   ```

   where`<remote.target.host>`has the value of each host name in your cluster.

6. If the following warning message displays during your first connection:`Are you sure you want to continue connecting (yes/no)?`Enter`Yes`.

7. Retain a copy of the SSH Private Key on the machine from which you will run the web-based Ambari Install Wizard.

   | ![](https://docs.hortonworks.com/HDPDocuments/Ambari-2.5.0.3/bk_ambari-installation/common/images/admon/note.png "\[Note\]") | Note |
   | :--- | :--- |
   |  | It is possible to use a non-root SSH account, if that account can execute`sudo`without entering a password. |



