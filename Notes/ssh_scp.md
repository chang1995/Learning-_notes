# SSH_SCP

## 1.SSH的安装

```
$ sudo apt install ssh
```

## 2. 启用本机SSH服务

```
$ sudo service ssh start
```

启用SSH服务后,允许linux远程连接到本机.

## 3. 检查SSH服务的状态

```
$ ps -e | grep ssh
```

如果服务已经启动，则可以看到“sshd”，否则表示没有安装服务，或没有开机启动。

![image-20200623162338263.png](https://github.com/chang1995/Learning_Notes/blob/master/picture_library/image-20200623162338263.png?raw=true)

## 4. Config SSH

```
$ sudo vim /etc/ssh/sshd_config
```

![image-20200623164619130.png](https://github.com/chang1995/Learning_Notes/blob/master/picture_library/image-20200623164619130.png?raw=true)

端口号默认为22,可以对其中的参数进行修改. 修改完成后,重启SSH服务即可生效.

```
$ sudo service ssh restart
```

## 5. 查看本机ip地址,利用SSH进行访问

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

## 6. 关闭SSH服务

```
$ sudo service ssh stop
```

![image-20200624104440874](/home/xuhui/.config/Typora/typora-user-images/image-20200624104440874.png)

在关闭SSH服务后,利用` $ ps -e | grep ssh`可以查看到服务已经关闭.



## 7. SCP的使用

利用scp可以从服务器上,上传或者下载文件.**远方服务器需要开启SSH服务.**		

例如:从`服务器用户名:xuhui`,`IP地址:10.9.27.161`拷贝文件执行以下命令. 拷贝文件夹时,使用`scp -r`

```
$ scp test.txt xuhui@10.9.27.161:/home/xuhui/Desktop/       # 将本地方的文件拷贝到远方
```

```
$ scp xuhui@10.9.27.161:/home/xuhui/Desktop/test.txt .		# 将远方的文件拷贝到本地当前目录下
```