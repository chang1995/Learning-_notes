# sam-ba

## 1. Download

在官网上下载合适的版本  

网址: https://www.microchip.com/

右上角搜索框中搜索输入`sam-ba`进行查找,选择合适版本下载,然后进行解压.

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

## 4. 注意事项

MCU与SAM-BA的连接是由于芯片内有一段固化的代码运行起来后才会检测到目标板并建立连接.   
**假设现在你烧写了Bootstrap进去，芯片上电后发现有可运行的代码，从而就不执行片内固化的那个代码. 因此,就无法与SAM-BA建立连接**.解决方法主要有以下几个方面:  

* 在开发板上已经预留了处理这个问题的硬件，即有个按钮,一旦这个按钮按下，则清除flash中的所有代码，以便让芯片上电后执行其片内固化的代码。当    然，这个要bootstrap里面软件的支持,就是bootstrap检测按钮是否按下,若按下则清除. 这样,芯片上电检测不到有效的、可执行的代码就会 执行片内固化的部分.
* 还有一个比较不专业的办法，但很有效。如果开发板没有设计按钮,也没有在bootstrap中设计清除代码.但我这里有一招就是短接nand flash（如果板子上没有nor flash和data flash）的地址线，大概是42脚左右的位置都行.这样做的目的就是让芯片不能正确的将nand flash中的代码正确搬运到sdram中，因此芯片内的固化代码依然会执行。这就解决了和SAM-BA不能连接的问题.

![image-20200623111457651.png](https://github.com/chang1995/Learning_Notes/blob/master/picture_library/image-20200623111457651.png?raw=true)