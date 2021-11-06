---
title: My first piece of blog
date: 2021-11-03 21:50:55
tags: CentOS7安装node.js
---

# CentOS7安装node.js

## 一、环境介绍
系统版本：CentOS Linux 7 (Core)

内核版本：Linux version 4.16.13-1.el7.elrepo.x86_64

 

## 二、安装node.js
#### 1、确认依赖环境

确认服务器有nodejs编译及依赖相关软件，如果没有可通过运行以下命令安装。

```
yum -y install gcc gcc-c++ openssl-devel
```



#### 2、下载NodeJS源码包并解压

进入要存放下载资源的目录，本文存放在/usr/local/src/目录下。然后执行命令下载源码包：

```
wget http://nodejs.org/dist/v8.11.1/node-v8.11.1-linux-x64.tar.gz
```

解压

```
tar -zxvf node-v8.11.1-linux-x64.tar.gz
```

解压完成后重命名文件夹，将文件夹重命名为node（非必须）：

```
mv node-v8.11.1-linux-x64 node
```



#### 3、测试是否安装成功

进入 node 目录下的bin目录，执行 ls命令：

```
cd node/bin && ls 
```

会看到node和npm，使用如下命令：

```
./node -v
```

如果看到v8.11.1，则说明安装成功。



#### 4、设置全局

现在node和npm还不能全局使用，我们要添加环境变量，首先在 root 目录下找到 .bash_profile 文件，编辑：

```
vim ~/.bash_profile
```

找到PATH=$PATH:$HOME/bin，在后面添加路径"：/usr/local/src/node/bin"（注意：路径用冒号隔开）。

如果不想用vim命令，可以在宝塔中直接修改。

保存修改，然后使用如下命令使配置生效：

source ~/.bash_profile

#### 5、验证全局

在任意位置执行node -v命令，查看是否输出node版本号，如果是，则全局设置生效。现在可以在任何目录下执行node和npm命令了！

 

## 三、其他（非必须）

#### 1、为npm添加淘宝镜像

```
npm config set registry https://registry.npm.taobao.org
```

#### 2、使用淘宝npm镜像的cnpm（本文使用的方法）

因为下载都是国外服务器很慢会掉线，我们需要使用淘宝的npm镜像cnpm。执行命令：

```
npm install -g cnpm --registry=https://registry.npm.taobao.org
```

启用淘宝的npm镜像cnpm，注意：启用后当我们要输入npm命令时，就需要输入cnpm



————————————————
版权声明：本文为CSDN博主「caoruichn」的原创文章。
原文链接：https://blog.csdn.net/qq_38591756/article/details/82830121

