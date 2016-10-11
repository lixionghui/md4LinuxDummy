
使用crontab运行定时任务的方法，分享给大家

最近将优化部的代码做为定时任务放到我们的R服务器上在跑。后面我们的R代码部署都可以参考此方法流程。定时任务可以各自用户分别定义，在登录服务器后可以开启服务

/sbin/service crond start //启动服务
/sbin/service crond stop //关闭服务
/sbin/service crond restart //重启服务
/sbin/service crond reload //重新载入配置

service crond status  //观察服务状态

crontab -l //观察本用户的定时任务配置
crontab -e //配置本用户的定时任务

以下是本人的一个配置示范，表示在每周日的晚上8点0分定时执行此任务，即pis脚本
0 20 * * 0 sh pis.sh

pis是一个shell脚本，可以顺序运行多个R脚本。其中pis_bi是李鹏之前为优化团队调试的代码，之后加上了log代码，当任务运行完成，会在本地写入log.txt。

#!/bin/sh
. /etc/profile
. ~/.bash_profile
cd /home/lipeng/lp/l1-07
Rscript pis_bi.R
Rscript log.R

crontab定时任务写法：
基本格式:

*  *　*　*　*　　command
分　时　日　月　周　 命令

第1列表示分钟1～59 每分钟用*或者*/1表示
第2列表示小时1～23（0表示0点）
第3列表示日期1～31
第4列 表示月份1～12
第5列标识号星期0～6（0表示星期天）
第6列要运行的命令

