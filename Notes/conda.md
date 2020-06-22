# conda 使用教程(linux) 

2020/6/15

## 1.下载安装

### 1.1下载

所有版本镜像(清华大学开源镜像网站)：https://mirrors.tuna.tsinghua.edu.cn/anaconda/archive/  		

从中选择合适版本的镜像下载.如 [Anaconda3-5.3.1-Linux-x86_64.sh](https://mirrors.tuna.tsinghua.edu.cn/anaconda/archive/Anaconda3-5.3.1-Linux-x86_64.sh)

### 1.2安装

~~~
$ sudo bash Anaconda3-5.3.1-Linux-x86_64.sh 
~~~

然后根据提示,进行安装

## 2.相关命令

### 2.1查看所有环境

```
$ conda env list
```

~~~
$ conda info -e
~~~

以上两个命令均可

### 2.2创建一个新的虚拟环境

```
$ conda create -n env_name python=3.6
```

指定Python的版本,否则是Python默认的版本

### 2.3激活虚拟环境

```
$ conda activate env_name
```

```
$ source activate env_name		# linux
```

```
$ activate env_name		# windows
```

### 2.4退出虚拟环境

```
$ source deactivate		# linux
```

```
$ deactivate env_name		# windows
```



### 2.5删除虚拟环境

```
$ conda remove -n yourEnvname --all	  # 删除虚拟环境
```

```
$ conda remove --name $env_name  $package_name 	 # 删除环境中的某个package
```


