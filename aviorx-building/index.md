# Aviorx 构建



## 前言

基于docker-compose构建Aviorx服务站点.

[AviorX]^(安全可靠的企业应用)
<!--more-->

## 环境

1. JDK 1.8
2. CentOS 7
3. docker 1.13.1
4. docker-compose 1.24.1

## 问题

1. 执行 docker-compose up -d 后, nacos不能正常访问.错误日志显示,mysql数据库不能连接.
 初步怀疑是docker的启动顺序造成的.  nacos启动时,mysql数据库还未能正常启动.
 查询工单未能发现相同问题.
 使用docker-compose build命令后,nacos能正常访问. 但是,mysql容器下面的xxl-job-admin的日志中, 仍然有数据库不能访问的信息. (以后要详细调查)

2. 核心服务[cloud-upms]不能启动.
 发现日志中包含下列信息
```
 No typehandler found for property authorizedGrantTypes
```
根据工单系统中[810](https://git.pig4cloud.com/pig/pigx/issues/810)中描述,添加[application-dev.yml]中下列内容
```
  type-handlers-package:  com.xxx.yyy.common.data.handler
```

## 然后

未完待续...
