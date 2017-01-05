# nginx 命令

### 测试
返回配置文件路径，并验证配置文件语法是否正确
```linux
nginx -t 
```
### 执行操作
```linux
nginx -s signal
```

其中，信号可以是下列之一：
```linux
stop — fast shutdown

quit — graceful shutdown

reload — reloading the configuration file

reopen — reopening the log files
```
 

在配置文件中所作的更改不会被应用，直到命令重新配置被发送到nginx的或重新启动。要重新加载配置，执行：
```linux
nginx -s reload
```
