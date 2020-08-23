linux 使用ssh key进行登陆

1.创建key

```
ssh-keygen -t rsa #回车
#    Enter file in which to save the key (/root/.ssh/id_rsa): #默认即可
#    Enter passphrase (empty for no passphrase): #输入密码
#    Enter same passphrase again: #再输入一遍保护密码
#    Your identification has been saved in /root/.ssh/id_rsa.
#    Your public key has been saved in /root/.ssh/id_rsa.pub.
#    The key fingerprint is:
#    SHA256:BQLRxhkpfq6H4LdXrAInx/nFS7OFqb+MmyoCBABkVUI root@Fuyoo
#    The key's randomart image is:
#    +---[RSA 2048]----+
#    |*ooE+*o+.        |
#    |o   o *. .       |
#    |.  . o    .      |
#    | .  . .  .       |
#    |.  . + oSo       |
#    |. + = . X .      |
#    |.. * + * =       |
#    |. o = *+o        |
#    | . oo*+o+.       |
#    +----[SHA256]-----+
1234567891011121314151617181920
```

2.将公钥导入到vps

```
cat /root/.ssh/id_rsa.pub >> /root/.ssh/authorized_keys
1
```

3.修改SSHD的配置文件/etc/ssh/sshd_config

```
#RSAAuthentication yes #去掉注释
#PubkeyAuthentication yes #去掉注释
#AuthorizedKeysFile .ssh/authorized_keys #去掉注释
123
```

4.重启服SSH务 后 进行测试

```
service sshd restart
1
```

5.测试完成后关闭root用户密码登陆

```
PasswordAuthentication yes #修改为 PasswordAuthentication no
1
```

6.保存重启

```
service sshd restart
1
```

1. 后续
   备份私钥后删除服务器端的私钥