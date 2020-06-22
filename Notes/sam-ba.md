# sam-ba

## 1. Download

在官网上下载合适的版本

网址:[https://www.microchip.com/developmenttools/ProductDetails/SAM-BA%20In-system%20Programmer](https://www.microchip.com/developmenttools/ProductDetails/SAM-BA In-system Programmer)

然后进行解压

## 2. boot from Flash

By default, samv7 boots from ROM, we want it boot from Flash. Using SAM-BA we can set a non-valotile config bit on the chip so it **boots from Flash after power cycle.**

```
$ cd ~/Downloads/sam-ba_3.3.1
```

```
$ ./sam-ba -p usb -b samv71-xplained -a bootconfig -c writecfg:bootmode:flash
```

需要在下载的sam_ba的目录下运行,执行完命令后重新上电即可从flash中启动.

![image-20200617111006959.png](https://github.com/chang1995/Learning_Notes/blob/master/picture_library/image-20200617111006959.png?raw=true)

## 3. loading boot_loader to Flash

```
$ ./sam-ba -p usb -b samv71-xplained -a internalflash -c erase -c write:/home/xuhui/sub/dashboard_indicator/embedded-sw_test/bazel-bin/products/dashboard_indicator_loader/dashboard_indicator_loader_app.bin 
```

将自己的Bin文件下载进flash中,同样需要在sam-ba的目录下进行下载.

![image-20200617111224462.png](https://github.com/chang1995/Learning_Notes/blob/master/picture_library/image-20200617111224462.png?raw=true)

![image-20200617111357651.png](https://github.com/chang1995/Learning_Notes/blob/master/picture_library/image-20200617111357651.png?raw=true)

