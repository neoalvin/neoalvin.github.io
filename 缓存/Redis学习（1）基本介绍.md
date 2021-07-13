# Redis学习（1）基本介绍

## 1.Redis介绍

Redis是一个使用C语言编写的、开源的、可支持内存和持久化存储的高性能Key-Value数据库。

## 2.Redis特点

（1）**高性能**，读取速度快；

（2）**支持丰富的数据机构**，如String、List、Set、Hash等；

（3）所有**操作支持原子性**，要么成功执行，要么不执行；多个操作支持事务，也是原子性。

（4）**丰富的特性**，可用于缓存、消息，按key设置过期时间，到期后数据会自动删除；

（5）支持**持久化存储**，可以将内存中的数据存储到磁盘中，重启时可以再次加载使用；

（6）支持**数据备份**。

## 3.Redis安装

**（1）下载地址**

windows: https://github.com/tporadowski/redis/releases

linux: https://redis.io/download

**（2）基本命令**

将redis根目录配置到环境变量中，可执行下面命令启动redis服务器：

```shell
redis-server
```

启动redis客户端：

```shell
redis-cli -h 127.0.0.1 -p 6379
```

设置键值对：

```shell
set name alvin
```

读取键值对：

```shell
get name
```

