Ambari Server 需要在节点机上安装agent，因此需要可以无密码登录ssh的权限来运行脚本。当然也可以手动在每台机上安装agent。

1. 在Ambari服务器上生成公钥.

2. ```bash
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
   cat id_rsa.pub >> authorized_keys
   ```

5. 需要设置节点机上的目录权限

   ```
   chmod 700 ~/.ssh
   ```

   ```
   chmod 600 ~/.ssh/authorized_keys
   ```

6. 从服务器运行命令测试，如果不需要任何其他操作，就可以ssh登录就行了。

   ```
   ssh root@<remote.target.host>
   ```

7. 如果出现下面的提示，选yes，这个提示应该只出现一回，再次测试应该不会出现:`Are you sure you want to continue connecting (yes/no)?`

8. 备份一份密钥，请使用root用户，不用root也是可以的，但是可能有很多需要设置的地方，不建议。



