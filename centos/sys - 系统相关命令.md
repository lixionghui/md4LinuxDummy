

操作系统信息
```
uname -a # 显示电脑以及操作系统的相关信息
cat /proc/version # 输出正在运行的内核版本，包含gcc版本
cat /etc/issue # 输出发行版本信息
```


```
pwd # 获取当前路径
```

```
chmod 777 - R dir # 修改权限

chown -R username directory  # 修改文件夹的用户所有者
chgrp -R groupname directory # 修改文件夹的用户组所有者
```


查看磁盘空间大小
```
df -h # 参数 -h 表示使用「Human-readable」的输出，也就是在档案系统大小使用 GB、MB 等易读的格式。
df -lh

df -T # 可以用来查看分区的文件系统
```
上面的命令输出的第一个字段（Filesystem）及最后一个字段（Mounted on）分别是档案系统及其挂入点。我们可以看到 /dev/sda1 这个分割区被挂在根目录下。

接下来的四个字段 Size、Used、Avail、及 Use% 分别是该分割区的容量、已使用的大小、剩下的大小、及使用的百分比。


查看目录下各个文件及目录占用空间大小
```
du -sh * # 查看当前目录下各个文件及目录占用空间大小
```



删除文件
```
rm -f *      # 删除当前目录下的所有文件，不会删除目录
rm -rf log      # 强制删除文件，包括目录

rm -rf log/* # 删除logs文件夹下的所有文件，而不删除文件夹本身
```


监控实时进程使用情况
```
top -M
htop   # htop 是更友好的程序，需安装
```
在交互界面中使用 shift + m ，可按内存使用大小排序







监控实时进程使用情况
```
yum update # 操作系统更新（大版本内更新）
```
在交互界面中使用 shift + m ，可按内存使用大小排序
