# 通用部署方案

## 基础镜像
### php
- 基于 php:7.2-fpm
- 常用及自定义扩展安装

### nginx
- 基于 nginx:latest

### redis
- 基于 centos:centos7
- redis-5.0.7

### mysql
- 基于 mysql:5.7

### mycat
- jdk-1.8.0_20
- mycat-1.6.7.3

### haproxy_keepalived
- 基于 haproxy:latest
- 安装keepalived

### etcd
- 基于 quay.io/coreos/etcd

## 部署方案
### lnmp
nginx + mysql + php 基础环境
- nginx
外部端口：80->80
- mysql
外部端口：3306->3306
- php
外部端口：9000->9000

### redis主从
- m_79:
内部ip: 192.168.1.79
外部端口：6379->6379
- s_80
内部ip: 192.168.1.80
外部端口：6380->6379
- s_81
内部ip: 192.168.1.81
外部端口：6381->6379

### redis哨兵
- sentinel_179
内部ip: 192.168.1.179
外部端口：26379->26379
- sentinel_180
内部ip: 192.168.1.180
外部端口：26380->26379
- sentinel_181
内部ip: 192.168.1.181
外部端口：26381->26379

### redis集群
- redis_200
内部ip: 192.168.1.200
外部端口：6320->6379 16320->16379
- redis_201
内部ip: 192.168.1.201
外部端口：6321->6379 16321->16379
- redis_202
内部ip: 192.168.1.202
外部端口：6322->6379 16322->16379
- redis_200
内部ip: 192.168.1.203
外部端口：6323->6379 16323->16379
- redis_204
内部ip: 192.168.1.204
外部端口：6324->6379 16324->16379
- redis_205
内部ip: 192.168.1.205
外部端口：6325->6379 16325->16379
- redis_206
内部ip: 192.168.1.206
外部端口：6326->6379 16326->16379
- redis_207
内部ip: 192.168.1.207
外部端口：6327->6379 16327->16379
- redis_208
内部ip: 192.168.1.208
外部端口：6328->6379 16328->16379

### mycat高可用集群
- keepalived
外部vip：192.168.220.100
- haproxy_166
内部ip: 192.168.10.166
外部端口：8166->8166 1080->1080
- haproxy_167
内部ip: 192.168.10.167
外部端口: 8167->8166 1081->1080
- mycat_66
内部ip: 192.168.10.66
外部端口: 8066->8066 9066->9066
- mycat_67
内部ip: 192.168.10.67
外部端口: 8067->8066 9067->9066
- mysql_m_6
内部ip: 192.168.10.6
外部端口: 3306->3306
- mysql_s_7
内部ip: 192.168.10.7
外部端口: 3307->3306
- mysql_s_8
内部ip: 192.168.10.8
外部端口: 3308->3306

### etcd集群
- etcd_10
内部ip: 192.168.20.10
外部端口: 2310->2379 2311->2380
- etcd_20
内部ip: 192.168.20.20
外部端口: 2320->2379 2321->2380
- etcd_30
内部ip: 192.168.20.30
外部端口: 2330->2379 2331->2380
