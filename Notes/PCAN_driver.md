# PCAN

## 1. Download

PCAN 需要**peak can driver** 和 **PCAN-Basic for Linux** 进行.   

* [peak can driver](http://www.peak-system.com/fileadmin/media/linux/index.htm) : http://www.peak-system.com/fileadmin/media/linux/index.htm

* [PCAN-Basic for Linux](https://www.peak-system.com/quick/BasicLinux) : https://www.peak-system.com/quick/BasicLinux

![image-20200624172828777.png](https://github.com/chang1995/Learning_Notes/blob/master/picture_library/image-20200624172828777.png?raw=true)

注: 可以继续安装页面下端的pcanview软件,对can线上的数据进行调试和监控.

## 2. 安装

将安装包解压后,参考解压缩后文件中的` README` 文件进行安装.  

安装peak can driver

```
$ cd peak-linux-driver-8.10.0
$ make clean all
$ make -C driver clean
$ make -C lib clean
$ make -C libpcanbasic clean
$ make -C driver all
$ make -C lib all
$ make -C libpcanbasic all
$ sudo make install   
```

安装 PCAN-Basic 

```
$ cd PCAN-Basic_Linux-4.3.4/libpcanbasic/pcanbasic
$ make clean
$ make
$ sudo make install
```

**注: 安装完驱动后,需要重新插拔USB接口才能使用.**

## 2. Python-can

安装好驱动后,可以下载Python-can模块,调用进行can的Python编程.

```
$ pip install python-can
```

如果下在失败,可以指定稍低版本的进行下载

```
$ pip install "python-can==3.1.1"
```

可以参照官网或者github进行测试,调用借口进行编程.

官网 : https://python-can.readthedocs.io/en/master/

github: https://github.com/hardbyte/python-can