

## 操作系统

Linux内核与发行版
```
cat /proc/version # 输出正在运行的内核版本，包含gcc版本
cat /etc/redhat-release # 输出发行版本信息，CentOS版本
```

包管理器
```
yum update # 操作系统更新（大版本内更新）
```


## CPU
如何查看linux系统和CPU型号，类型和大小
```
cat /proc/cpuinfo
```

总核数 = 物理CPU个数 X 每颗物理CPU的核数 
总逻辑CPU数 = 物理CPU个数 X 每颗物理CPU的核数 X 超线程数

查看物理CPU个数
```
cat /proc/cpuinfo| grep "physical id"| sort| uniq| wc -l
```

查看每个物理CPU中core的个数(即核数)
```
cat /proc/cpuinfo| grep "cpu cores"| uniq
```

查看逻辑CPU的个数
```
cat /proc/cpuinfo| grep "processor"| wc -l
```

## 内存
如何查看linux 系统内存大小的信息，可以查看总内存，剩余内存，可使用内存等信息 
```
cat /proc/meminfo
```

## 磁盘
查看磁盘空间大小
```
df -h # 参数 -h 表示使用「Human-readable」的输出，也就是在档案系统大小使用 GB、MB 等易读的格式。
df -lh

df -T # 可以用来查看分区的文件系统
```
上面的命令输出的第一个字段（Filesystem）及最后一个字段（Mounted on）分别是档案系统及其挂入点。我们可以看到 /dev/sda1 这个分割区被挂在根目录下。

接下来的四个字段 Size、Used、Avail、及 Use% 分别是该分割区的容量、已使用的大小、剩下的大小、及使用的百分比。


查看目录下各个文件及目录占用空间大小。
du命令用于显示指定文件(夹)在磁盘中所占的空间信息
```
du -sh * # 查看当前目录下各个文件及目录占用空间大小
```

## 监控
监控实时进程使用情况
```
top -M
htop   # htop 是更友好的程序，需安装
```
在交互界面中使用 shift + m ，可按内存使用大小排序



## 路径
获取当前路径
```
pwd 
```

## 权限
修改权限
```
chmod 777 - R dir # 赋予所有权限

chown -R username directory  # 修改文件夹的用户所有者
chgrp -R groupname directory # 修改文件夹的用户组所有者
```


删除文件
```
rm -f *      # 删除当前目录下的所有文件，不会删除目录
rm -rf log      # 强制删除文件，包括目录

rm -rf log/* # 删除logs文件夹下的所有文件，而不删除文件夹本身
```









