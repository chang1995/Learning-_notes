# SSH 

# SSH

### 1.1 SSH的安装

```
$ sudo apt install ssh
```

### 1.2 启用本机SSH服务

```
$ sudo service ssh start
```

启用SSH服务后,允许linux远程连接到本机.

### 1.3 检查SSH服务的状态

```
$ ps -e | grep ssh
```

如果服务已经启动，则可以看到“sshd”，否则表示没有安装服务，或没有开机启动。

![image-20200623162338263.png](https://github.com/chang1995/Learning_Notes/blob/master/picture_library/image-20200623162338263.png?raw=true)

### 1.4 Config SSH

```
$ sudo vim /etc/ssh/sshd_config
```

![image-20200623164619130.png](https://github.com/chang1995/Learning_Notes/blob/master/picture_library/image-20200623164619130.png?raw=true)

端口号默认为22,可以对其中的参数进行修改. 修改完成后,重启SSH服务即可生效.

```
$ sudo service ssh restart
```

### 1.5 查看本机ip地址,利用SSH进行访问

```
$ ifconfig   # 查询本机IP地址
```

![image-20200623165610253.png](https://github.com/chang1995/Learning_Notes/blob/master/picture_library/image-20200623165610253.png?raw=true)

```
$ ssh xuhui@10.9.27.161
```

用其他电脑利用SSH访问,输入密码后远程登录本机.登录远程服务器,原理相同.

![image-20200623170717491.png](https://github.com/chang1995/Learning_Notes/blob/master/picture_library/image-20200623170717491.png?raw=true)

![image-20200623170819214.png](https://github.com/chang1995/Learning_Notes/blob/master/picture_library/image-20200623170819214.png?raw=true)