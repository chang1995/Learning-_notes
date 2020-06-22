# arecord、aplay 实现录音和播放

​																																						2020/6/15

## 1.查看录音设备

```
$ arecord -l
```

![image-20200615164758374.png](https://github.com/chang1995/Learning_Notes/blob/master/picture_library/image-20200615164758374.png?raw=true)

## 2.录音

```
$ arecord -D hw:2,0 -d 10 -r 48000 -f S16_LE  test.wav
```

参数解析  
-D 指定了录音设备，2,0 是card 2 device 0的意思  
-d 指定录音的时长，单位时秒(如果不加,可以使用Ctrl + C结束录音)  
-f 指定录音格式，通过上面的信息知道只支持 cd cdr dat   
-r 指定了采样率，单位时Hz  
-t 指定生成的文件格式  

## 3.播放

```
$ aplay test.wav 
```
