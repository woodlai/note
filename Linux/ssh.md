# ssh

## install：

```
yum install ssh
```

## start：

```
service sshd start
```

## login：

### Password（密码）

```
 ssh user@127.0.0.1
```

- `user` 是服务器 `用户名`
- `127.0.0.1` 是服务器 `ip`
- 回车，显示要输入密码：
- `user@127.0.0.1:`
- 输入密码,回车即可登录

### SSL（密钥）

#### windows

- 输入以下命令来生成 SSH 密钥对

```
ssh-keygen -t rsa -b 2048 -C "your_email@example.com"
```

按照提示操作，选择密钥文件存储位置，默认情况下将会存储在 `C:\Users\YourUsername\.ssh\id_rsa 和 C:\Users\YourUsername\.ssh\id_rsa.pub`

- 使用 Password 连接服务器
- 在远程服务器上打开 authorized_keys 文件，并将本地公钥的内容粘贴到文件的末尾。使用 vim 等编辑器来进行编辑

```
vim ~/.ssh/authorized_keys
```

- 测试 SSH 连接，如果成功连接，则不再需要输入密码
