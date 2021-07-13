# Gitbook+Github Pages搭建个人文档中心全流程

## 1.安装Gitbook

参考[Gitbook安装](Gitbook安装.md)

## 2.Gitbook使用

**（1）初始化gitbook**

```shell
gitbook init
```

**（2）生成目录**

参考[Gitbook生成目录SUMMARY文件](Gitbook生成目录SUMMARY文件.md)

**（3）生成静态网页到docs目录下**

```shell
gitbook build ./ docs
```

## 3.提交到Github