# Windows安装MySQL方法

### 1.下载MySQL

https://downloads.mysql.com/archives/community/

### 2.修改配置文件

将下载的压缩包解压到适合的位置，在解压的目录下创建my.ini配置文件，编辑以下信息：

```ini
[client]
# 设置mysql客户端默认字符集
default-character-set=utf8
 
[mysqld]
# 设置3306端口
port = 3306
# 设置mysql的安装目录
basedir=D:\\CodeTools\\MySQL
# 设置 mysql数据库的数据的存放目录，MySQL 8+ 不需要以下配置，系统自己生成即可，否则有可能报错
datadir=D:\\CodeTools\\MySQL\\data
# 允许最大连接数
max_connections=20
# 服务端使用的字符集默认为8比特编码的latin1字符集
character-set-server=utf8
# 创建新表时将使用的默认存储引擎
default-storage-engine=INNODB
```

### 3.初始化数据库

（1）管理员方式打开命令行工具，切换到mysql目录

```shell
cd D:\CodeTools\MySQL\bin
```

（2）初始化数据库

```shell
mysqld --initialize --console
```

这一步可能会报错：由于找不到MSVCP120.dll,无法继续执行代码.重新安装程序可能会解决此问题。

解决方法：[安装windows运行库](https://www.microsoft.com/zh-CN/download/details.aspx?id=40784)

上面命令运行成功后，会输出mysql的临时登录密码，第一次登录数据库需要用到，成功登录之后可以修改密码，如下图：


（3）安装数据库服务

```shell
mysqld install
```

（4）启动数据库服务

```shell
net start mysql
```

### 4.登录数据库

```shell
mysql -u root -p
```

修改密码：

```sql
SET PASSWORD = "0000";
```

