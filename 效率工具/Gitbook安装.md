# Gitbook安装

# 1.安装nodejs和npm

下载地址：https://nodejs.org/zh-cn/download/

windows下可以直接通过msi安装，在命令行中执行下面命令表示安装成功：

```shell
PS C:\Windows\system32> node -v
v16.4.1
```

# 2.安装gitbook

```shell
npm install -g gitbook-cli
```

```shell
gitbook -V
```

这一步会出现下面的报错：

```
CLI version: 2.3.2
Installing GitBook 3.2.3
D:\CodeTools\NodeJS\node_global\node_modules\gitbook-cli\node_modules\npm\node_modules\graceful-fs\polyfills.js:287
      if (cb) cb.apply(this, arguments)
                 ^
TypeError: cb.apply is not a function
```

**问题原因：** gitbook对nodejs最新版本不支持，检查不通过

**解决方法：** 下面两种方法均能完美解决

（1）回退nodejs版本到10.23.0版本；

（2）打开报错的js文件（D:\CodeTools\NodeJS\node_global\node_modules\gitbook-cli\node_modules\npm\node_modules\graceful-fs\polyfills.js），注释掉62~64的三行代码，绕过检查：

```shell
  //fs.stat = statFix(fs.stat)
  //fs.fstat = statFix(fs.fstat)
  //fs.lstat = statFix(fs.lstat)
```
ps: 事实证明，如果想要正常使用gitbook还是乖乖回退nodejs的版本吧，第二种方法只能绕过安装的检查，但是后续使用仍然会有问题

