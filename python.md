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


# python基础教程

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

## 运算符

**算数运算符**

| 运算符 | 描述                                            | 实例                                               |
| ------ | ----------------------------------------------- | -------------------------------------------------- |
| +      | 加 - 两个对象相加                               | a + b 输出结果 30                                  |
| -      | 减 - 得到负数或是一个数减去另一个数             | a - b 输出结果 -10                                 |
| *      | 乘 - 两个数相乘或是返回一个被重复若干次的字符串 | a * b 输出结果 200                                 |
| /      | 除 - x除以y                                     | b / a 输出结果 2                                   |
| %      | 取模 - 返回除法的余数                           | b % a 输出结果 0                                   |
| **     | 幂 - 返回x的y次幂                               | a**b 为10的20次方， 输出结果 100000000000000000000 |
| //     | 取整除 - 返回商的整数部分（**向下取整**）       | `>>> 9//2 4 >>> -9//2 -5`                          |

**比较运算符**

| 运算符 | 描述                                                         | 实例                                     |
| ------ | ------------------------------------------------------------ | ---------------------------------------- |
| ==     | 等于 - 比较对象是否相等                                      | (a == b) 返回 False。                    |
| !=     | 不等于 - 比较两个对象是否不相等                              | (a != b) 返回 true.                      |
| <>     | 不等于 - 比较两个对象是否不相等。python3 已废弃。            | (a <> b) 返回 true。这个运算符类似 != 。 |
| >      | 大于 - 返回x是否大于y                                        | (a > b) 返回 False。                     |
| <      | 小于 - 返回x是否小于y。所有比较运算符返回1表示真，返回0表示假。这分别与特殊的变量True和False等价。 | (a < b) 返回 true。                      |
| >=     | 大于等于	- 返回x是否大于等于y。                           | (a >= b) 返回 False。                    |
| <=     | 小于等于 -	返回x是否小于等于y。                           | (a <= b) 返回 true。                     |

**赋值运算符**

| =    | 简单的赋值运算符 | c = a + b 将 a + b 的运算结果赋值为 c |
| ---- | ---------------- | ------------------------------------- |
| +=   | 加法赋值运算符   | c += a 等效于 c = c + a               |
| -=   | 减法赋值运算符   | c -= a 等效于 c = c - a               |
| *=   | 乘法赋值运算符   | c *= a 等效于 c = c * a               |
| /=   | 除法赋值运算符   | c /= a 等效于 c = c / a               |
| %=   | 取模赋值运算符   | c %= a 等效于 c = c % a               |
| **=  | 幂赋值运算符     | c **= a 等效于 c = c ** a             |
| //=  | 取整除赋值运算符 | c //= a 等效于 c = c // a             |

**运算符优先级**

| **                       | 指数 (最高优先级)                                      |
| ------------------------ | ------------------------------------------------------ |
| ~ + -                    | 按位翻转, 一元加号和减号 (最后两个的方法名为 +@ 和 -@) |
| * / % //                 | 乘，除，取模和取整除                                   |
| + -                      | 加法减法                                               |
| >> <<                    | 右移，左移运算符                                       |
| &                        | 位 'AND'                                               |
| ^ \|                     | 位运算符                                               |
| <= < > >=                | 比较运算符                                             |
| <> == !=                 | 等于运算符                                             |
| = %= /= //= -= += *= **= | 赋值运算符                                             |
| is is not                | 身份运算符                                             |
| in not in                | 成员运算符                                             |
| not and or               | 逻辑运算符                                             |

## 条件语句

Python条件语句是通过一条或多条语句的执行结果（True或者False）来决定执行的代码块。

Python程序语言指定任何非0和非空（null）值为true，0 或者 null为false。

Python 编程中 if 语句用于控制程序的执行，基本形式为：

```
if 判断条件：
    执行语句……
else：
    执行语句……
```

if 语句的判断条件可以用>（大于）、<(小于)、==（等于）、>=（大于等于）、<=（小于等于）来表示其关系。

当判断条件为多个值时，可以使用以下形式：

```
if 判断条件1:
    执行语句1……
elif 判断条件2:
    执行语句2……
elif 判断条件3:
    执行语句3……
else:
    执行语句4……
```

由于 python 并不支持 switch 语句，所以多个条件判断，只能用 elif 来实现，如果判断需要多个条件需同时判断时，可以使用 or （或），表示两个条件有一个成立时判断条件成功；使用 and （与）时，表示只有两个条件同时成立的情况下，判断条件才成功。

#!/usr/bin/python 

-*- coding: UTF-8 -*-

var = 100 
if ( var  == 100 ) : print "变量 var 的值为100" 
print "Good bye!"

## 循环语句

Python 提供了 for 循环和 while 循环（在 Python 中没有 do..while 循环）:

| 循环类型                                                     | 描述                                                   |
| ------------------------------------------------------------ | ------------------------------------------------------ |
| [while 循环](https://www.runoob.com/python/python-while-loop.html) | 在给定的判断条件为 true 时执行循环体，否则退出循环体。 |
| [for 循环](https://www.runoob.com/python/python-for-loop.html) | 重复执行语句                                           |
| [嵌套循环](https://www.runoob.com/python/python-nested-loops.html) | 你可以在while循环体中嵌套for循环                       |

------

循环控制语句

循环控制语句可以更改语句执行的顺序。Python支持以下循环控制语句：

| 控制语句                                                     | 描述                                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [break 语句](https://www.runoob.com/python/python-break-statement.html) | 在语句块执行过程中终止循环，并且跳出整个循环                 |
| [continue 语句](https://www.runoob.com/python/python-continue-statement.html) | 在语句块执行过程中终止当前循环，跳出该次循环，执行下一次循环。 |
| [pass 语句](https://www.runoob.com/python/python-pass-statement.html) | pass是空语句，是为了保持程序结构的完整性。                   |

## while循环语句

Python 编程中 while 语句用于循环执行程序，即在某条件下，循环执行某段程序，以处理需要重复处理的相同任务。其基本形式为：

```
while 判断条件(condition)：
    执行语句(statements)……
```

执行语句可以是单个语句或语句块。判断条件可以是任何表达式，任何非零、或非空（null）的值均为true。

当判断条件假 false 时，循环结束。

#!/usr/bin/python
count = 0
while (count < 9):
print 'The count is:', count
count = count + 1
print "Good bye!"

**无线循环**

#!/usr/bin/python

-*- coding: UTF-8 -*-

var = 1
while var == 1 :  # 该条件永远为true，循环将无限执行下去
num = raw_input("Enter a number  :")
print "You entered: ", num
print "Good bye!"

**循环使用 else 语句**

#!/usr/bin/python
count = 0
while count < 5:
print count, " is  less than 5"
count = count + 1
else:
print count, " is not less than 5"

**简单语句组**

类似 if 语句的语法，如果你的 while 循环体中只有一条语句，你可以将该语句与while写在同一行中， 如下所示：

#!/usr/bin/python
flag = 1
while (flag): print 'Given flag is really true!'
print "Good bye!"

## **for循环语句**

Python for循环可以遍历任何序列的项目，如一个列表或者一个字符串。

#!/usr/bin/python

-*- coding: UTF-8 -*-

for letter in 'Python':     # 第一个实例
print '当前字母 :', letter
fruits = ['banana', 'apple',  'mango']
for fruit in fruits:        # 第二个实例
print '当前水果 :', fruit
print "Good bye!"

**通过序列索引迭代**

#!/usr/bin/python

-*- coding: UTF-8 -*-

fruits = ['banana', 'apple',  'mango']
for index in range(len(fruits)):
print '当前水果 :', fruits[index]
print "Good bye!"

**循环使用else语句**

在 python 中，for … else 表示这样的意思，for 中的语句和普通的没有区别，else 中的语句会在循环正常执行完（即 for 不是通过 break 跳出而中断的）的情况下执行，while … else 也是一样。

#!/usr/bin/python

-*- coding: UTF-8 -*-

for num in range(10,20):  # 迭代 10 到 20 之间的数字
for i in range(2,num): # 根据因子迭代
if num%i == 0:      # 确定第一个因子
j=num/i          # 计算第二个因子
print '%d 等于 %d * %d' % (num,i,j)
break            # 跳出当前循环
else:                  # 循环的 else 部分
print num, '是一个质数'

## 循环嵌套

Python 语言允许在一个循环体里面嵌入另一个循环。

**Python for 循环嵌套语法：**

for iterating_var in sequence:    for iterating_var in sequence:       statements(s)    statements(s)

**Python while 循环嵌套语法：**

while expression:    while expression:       statement(s)    statement(s)

你可以在循环体内嵌入其他的循环体，如在while循环中可以嵌入for循环， 反之，你可以在for循环中嵌入while循环。

#!/usr/bin/python

#-*- coding: UTF-8 -*-

i = 2
while(i < 100):
j = 2
while(j <= (i/j)):
if not(i%j): break
j = j + 1
if (j > i/j) : print i, " 是素数"
i = i + 1
print "Good bye!"



## break语句

Python break语句，就像在C语言中，打破了最小封闭for或while循环。

break语句用来终止循环语句，即循环条件没有False条件或者序列还没被完全递归完，也会停止执行循环语句。

break语句用在while和for循环中。

如果您使用嵌套循环，break语句将停止执行最深层的循环，并开始执行下一行代码。

#!/usr/bin/python

#-*- coding: UTF-8 -*-

for letter in 'Python':     # 第一个实例
if letter == 'h':
break
print '当前字母 :', letter
var = 10                    # 第二个实例
while var > 0:              
print '当前变量值 :', var
var = var -1
if var == 5:   # 当变量 var 等于 5 时退出循环
break
print "Good bye!"

## continue语句

Python continue 语句跳出本次循环，而break跳出整个循环。

continue 语句用来告诉Python跳过当前循环的剩余语句，然后继续进行下一轮循环。

continue语句用在while和for循环中。

#!/usr/bin/python

#-*- coding: UTF-8 -*-

for letter in 'Python':     # 第一个实例
if letter == 'h':
continue
print '当前字母 :', letter
var = 10                    # 第二个实例
while var > 0:              
var = var -1
if var == 5:
continue
print '当前变量值 :', var
print "Good bye!"

## pass语句

Python pass 是空语句，是为了保持程序结构的完整性。

**pass** 不做任何事情，一般用做占位语句。

Python 语言 pass 语句语法格式如下：

#!/usr/bin/python

#-*- coding: UTF-8 -*-  -*- 

for letter in 'Python':
if letter == 'h':
pass
print '这是 pass 块'
print '当前字母 :', letter
print "Good bye!"

pass 一般用于占位置。

在 Python 中有时候会看到一个 def 函数:

```
def sample(n_samples):
    pass
```

该处的 pass 便是占据一个位置，因为如果定义一个空函数程序会报错，当你没有想好函数的内容是可以用 pass 填充，使程序可以正常运行。

