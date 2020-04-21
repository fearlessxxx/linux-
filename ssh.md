# ssh背景

- ssh客户端是一种使用Secure Shell(ssh)协议连接到运行了ssh服务端的远程服务器上。

- ssh是目前较可靠，专为远程登录会话和其他网络服务提供安全性的协议。
  - 有效防止远程管理过程中的信息泄漏
  - 传输 **数据加密**，能够防止DNS和IP欺骗
  - 传输 **数据压缩**，加快传输速度
- **OpenSSH** 是 SSH协议的免费开源实现。OpenSSH提供了服务端程序(**openssh-server**)和客户端工具(**openssh-client**)。
  - Mac和Linux中默认已安装ssh客户端，可直接在终端中使用ssh命令。Windows则需手动安装ssh客户端，较常用的Windows SSH客户端有PuTTY和XShell。

# ssh使用

​	想要从一台机器远程登录到另一台机器，登录的机器需要下载**openssh-client**，被登录的机器需要下载**openssh-server**。

## linux

### 作为登录电脑

Linux中默认已安装ssh客户端，但是有可能没有安装ssh服务端

1. 查看linux系统中是否安装了openssh-client

   ~~~shell
   yum list installed | grep openssh #检查是否安装了openssh-client
   ~~~

   ![](ssh.assets/image-20200420082836734.png)

   如果没有安装

   ~~~SHELL
   yum install openssh-client #安装openssh-client
   ~~~

2. 登录：`ssh`  用户名@被登录电脑ip地址

### 作为被登录电脑

1. 查看是否安装openssh-server

   ~~~shell
   yum list installed | grep openssh #检查是否安装了openssh-server
   #如果没有安装
   yum install openssh-server #安装openssh-server  
   ~~~

2. 开启服务端

   ~~~shell
   service sshd start
   ~~~











