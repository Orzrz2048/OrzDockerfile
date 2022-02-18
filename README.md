[TOC]

# 1. apue-ubuntu18
在 Ubuntu 18.04 下构建 UNIX 环境高级编程的学习环境
## 1.1 构建方法
> 构建时间较长
```shell
$ cd apue-ubuntu18
$ docker build -t apue:v1 .
```
## 1.2 使用方法
运行容器
```shell
$ docker run -dit -v /home/renzheng/dockerdata/apue:/root/data -P --name myapue apue:v1 /bin/bash
```
- d 按照 daemon 模式运行
- it 交互模式命令行
- v 数据卷映射，将宿主机 /home/renzheng/dockerdata/apue 映射到容器 /root/data
- P 端口映射

进入容器后编辑修改 sshd.conf 中的参数并开启 ssh
```shell
$ service ssh start
```
查看容器信息
```shell
$ docker inspect myapue
```
进入容器
```shell
$ docker exec -it myapue /bin/bash
```
# 2. httpd-dockerfile
Ubuntu18.04环境下编译httpd-2.4.37
