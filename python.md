# python

### python环境搭建

安装环境：

Windows 10 Pro
•VMWare Workstation 15 Pro
•CentOS Linux release 7.6.1810 (Core)
•root权限,所有操作都是在root用户下操作

***安装依赖和更新yum***

更新yum

yum -y update  （可选）

安装依赖

yum install zlib-devel bzip2-devel openssl-devel ncurses-devel sqlite-devel readline-devel tk-devel libffi-devel gcc make

**下载python包**

wget https://www.python.org/ftp/python/3.8.0/Python-3.8.0b3.tgz
解压

tar -xvf Python-3.8.0b3.tgz
编译

cd Python-3.8.0b3
配置编译的的路径

./configure --prefix=/opt/python/python-3.8.0              注：这里--prefix是指定编译安装的文件夹

优化选项（可选）

./configure --enable-optimizations

编译安装

make && make install

添加软连接

ln -s /opt/python/python-3.8.0 /usr/bin/python3


# python应用

## 操作方法

命令行输入python，进入python交互模式（CPython解释器）

提示符是`>>>`

交互模式下输入exit() 并回车，退出交互模式，进入命令行模式

## 中文编码

添加#-*- coding: UTF-8 -*-或# coding=utf-8

#!/usr/bin/python

#-*- coding: UTF-8 -*-

print（‘你好‘）

## 基础语法

**Python标识符**

在 Python 里，标识符由字母、数字、下划线组成。

在 Python 中，所有标识符可以包括英文、数字以及下划线(_)，但不能以数字开头。

Python 中的标识符是区分大小写的。

Python 可以同一行显示多条语句，方法是用分号 ; 分开，如：

```
>>> print ('hello');print ('runoob');
hello
runoob
```

**行和缩进**

缩进的空白数量是可变的，但是所有代码块语句必须包含相同的缩进空白数量，这个必须严格执行

if True:
​    print ("True")
else:
​    print ("False")

**多行语句**

Python语句中一般以新行作为语句的结束符。

但是我们可以使用斜杠（ \）将一行的语句分为多行显示，如下所示：

```
total = item_one + \
        item_two + \
        item_three
```

语句中包含 [], {} 或 () 括号就不需要使用多行连接符。如下实例：

```
days = ['Monday', 'Tuesday', 'Wednesday',
        'Thursday', 'Friday']
```

## 变量类型

变量存储在内存中的值。这就意味着在创建变量时会在内存中开辟一个空间。

基于变量的数据类型，解释器会分配指定内存，并决定什么数据可以被存储在内存中。

因此，变量可以指定不同的数据类型，这些变量可以存储整数，小数或字符。

**变量赋值**

Python 中的变量赋值不需要类型声明。

每个变量在内存中创建，都包括变量的标识，名称和数据这些信息。

每个变量在使用前都必须赋值，变量赋值以后该变量才会被创建。

等号（=）用来给变量赋值。

等号（=）运算符左边是一个变量名,等号（=）运算符右边是存储在变量中的值。例如：



#!/usr/bin/python

#-*- coding: UTF-8 -*-

counter = 100 # 赋值整型变量

miles = 1000.0 # 浮点型

name = "John" # 字符串

print counter

print miles

print name

以上实例中，100，1000.0和"John"分别赋值给counter，miles，name变量。

运行结果为

```
100
1000.0
John
```

**多个变量赋值**

Python允许你同时为多个变量赋值。例如：

a = b = c = 1

以上实例，创建一个整型对象，值为1，三个变量被分配到相同的内存空间上。

您也可以为多个对象指定多个变量。例如：

a, b, c = 1, 2, "john"

以上实例，两个整型对象 1 和 2 分别分配给变量 a 和 b，字符串对象 "john" 分配给变量 c。

**标准数据类型**

在内存中存储的数据可以有多种类型。

例如，一个人的年龄可以用数字来存储，他的名字可以用字符来存储。

Python 定义了一些标准类型，用于存储各种类型的数据。

Python有五个标准的数据类型：

- Numbers（数字）
- String（字符串）
- List（列表）
- Tuple（元组）
- Dictionary（字典）

