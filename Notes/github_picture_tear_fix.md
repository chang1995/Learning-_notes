# github图片撕裂的解决方法

## 1. 查看IP是否修改

* 登录https://www.ipaddress.com/  查看 `raw.githubusercontent.com`的IP地址，判断IP是否更改。

![image-20200625231137743](/home/cxh/.config/Typora/typora-user-images/image-20200625231137743.png)

---

![image-20200625231654172](/home/cxh/.config/Typora/typora-user-images/image-20200625231654172.png)

## 2. 修改host文件恢复正常

修改host文件恢复正常

Win：`C:\Windows\System32\drivers\etc\hosts`

Mac: `/etc/hosts`

Linux:` /etc/hosts`

在hosts文件最后追加（或者修改）:

```
# GitHub raw & image
199.232.68.133 raw.githubusercontent.com 
```

注：Win如何修改hosts文件请参考https://www.baidu.com/link?url=ms44btUuQ4O5PIz3ABd02z1PSxc6gdJ3agjA2ARsbYd4gKQyHFpAdpYsTXrL_34v71xQG8oBdyuXbi5B18mfJQCE3aCkc_A98OW-9dzlf9u&wd=&eqid=dc7d38df000ceaa2000000035ef4c176

