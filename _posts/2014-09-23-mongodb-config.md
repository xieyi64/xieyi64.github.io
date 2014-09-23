---
layout: postlayout
title: Mongodb配置文件
categories: [数据库]
tags: [mongodb]
---
mongodb 默认配置文件

##配置示例

~~~ ini
#SERVER
fork = true
port = 7001
quiet = true
dbpath = /data/mongodb/mongodb7001
logpath = /data/mongodb/mongodb7001/log/mongod.log
logappend = true
journal = true
nohttpinterface = true
directoryperdb = true
keyFile = /data/mongodb/mongodb7001/keyFile

#SLOW_LOG
profile = 1
slowms = 500

#RS
replSet = 7001
oplogSize = 20480

#SCO
#configsvr = true
#configdb = MSCHOST
~~~
