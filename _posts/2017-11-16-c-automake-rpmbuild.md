---
layout: post
title: "C工程的自动化构建"
date: 2017-11-16 23:09:00 +0800
categories: C语言
tag: C
---
# configure.ac

### autoreconf == (autoscan autoconf autoheader automake)
```
# 详细步骤
(empty) ---[autoscan]---> configure.scan ------> configure.ac
1. configure.ac ---[aclocal]---> aclocal.m4
2. configure.ac + aclocal.m4 ---[autoconf]---> configure
3. configure.ac + Makefile.am ---[automake]--> Makefile.in
4. Makefile.in ---(configure)---> Makefile
# 一步到位
configure.ac + Makefile.am ---[autoreconf]--> Makefile.in
```

### configure.ac
```
# 必须，限定autoconf最低版本号
AC_PREREQ([2.63])

# 必须，指定程序包名、版本号，包管理人联系邮箱
AC_INIT(helloworld, 1.0, qinglucklin@foxmail.com)

# 必须，配置该宏，用于运行许多宏，辅助生成Makefile
AM_INIT_AUTOMAKE

# 必须，指定配置头文件
AC_CONFIG_HEADER([include/config.h])

# 非必须，指定存放一些辅助脚本的目录，automake将会从该目录查找这些辅助脚本
AC_CONFIG_AUX_DIR(cfgaux)

# 
AC_CONFIG_FILES(Makefile)

# 
AC_OUTPUT

```

# Makefile.am

# rpm.spec

# 制作libev的rpm包

# 制作hiredis的rpm包

# 制作nginx的rpm包
