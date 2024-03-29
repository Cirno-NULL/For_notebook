# 基础语法

## 编码

默认情况下`python3`源码文件以`utf-8`编码\
所有字符都是`unicode`字符串 可以通过首行指定不同编码

```python
# -*- coding: cp-1252 -*-
```

## 标识符

* 第一个字符必须是字母表中字符或下划线`_`
* 标识符的其他部分由字母、数字和下划线组成
* 标识符对$$\color{red}{大小写敏感}$$
* python3允许中文作变量名，**非ASCII标识符**也是允许的。

#### 一些不在语言内的通用规定

* 大驼峰
* 小驼峰
* 下划线

## 保留字

保留字即关键字

```py
>>> import keyword
>>> keyword.kwlist
['False', 'None', 'True', 'and', 'as', 'assert', 'break', 'class', 'continue', 'def', 'del', 'elif', 'else', 'except', 'finally', 'for', 'from', 'global', 'if', 'import', 'in', 'is', 'lambda', 'nonlocal', 'not', 'or', 'pass', 'raise', 'return', 'try', 'while', 'with', 'yield']
```

## 注释

单行注释使用`#` 多行注释使用`''''''`或者`""""""`

```python
'''
print("testz")
'''

#这里是单行注释
#组合起来就是开关注释

'''''''
print("testa")
'''
print("testb")
#'''

'''
print("testac")
'''
print("testd")
#'''


'''''''
print("teste")
#'''

'''
print("testf")
#'''
```

## 行与缩进

python的代码块不再使用`{}`表示代码块    
取而代之的是缩进    
缩进的空格数是可变的    
但是同一个代码块的语句必须包含相同的缩进空格数。    

* tab和四个空格看起来相同，但是不是相同的缩进。

```py
if True:
    print ("True")
else:
    print ("False")


if True:
    print ("Answer")
    print ("True")
else:
    print ("Answer")
  print ("False")    # 缩进不一致，会导致运行错误
```

## 多行语句

Python 通常是一行写完一条语句   
但是如果语句很长的话    
可以使用反斜杠`\`来实现多行语句   
括号内的不需要使用`\`

```py
total = item_one + \
        item_two + \
        item_three

total = ['item_one', 'item_two', 'item_three',
        'item_four', 'item_five']
```

## 变量类型

### 数字类型

python中数字有四种类型：整数、布尔型、浮点数和复数

| 类型           | 释义                                                           |
| ------------ | ------------------------------------------------------------ |
| int          | <p>1<br>只有一种整数类型<code>int</code><br>表示为长整型<br>没有Long这种说法</p> |
| bool (布尔)    | <p>True<br>False</p>                                         |
| float (浮点数)  | <p>1.23<br>3E-2</p>                                          |
| complex (复数) | <p>1 + 2j<br>1.1 + 2.2j</p>                                  |

### 字符串

* Python 中单引号 ' 和双引号 " 使用完全相同。
* 使用三引号(`'''` 或 `"""`)可以指定一个多行字符串。
* 转义符 `\`。
* 反斜杠可以用来转义，使用 r 可以让反斜杠不发生转义。
  * 如 `r"this is a line with \n"` 则  会显示，\
    并不是换行。
* 字符串可以用 + 运算符连接在一起
  * 用 \* 运算符重复。
* Python 中的字符串有两种索引方式，
  * 从左往右以 0 开始，从右往左以 -1 开始。
* Python 中的字符串不能改变。
* Python 没有单独的字符类型
  * 一个字符就是长度为 1 的字符串。
* 字符串的截取的语法格式如下：变量\[头下标:尾下标:步长]

```python
str='123456789'
 
print(str)                 # 输出字符串
print(str[0:-1])           # 输出第一个到倒数第二个的所有字符
print(str[0])              # 输出字符串第一个字符
print(str[2:5])            # 输出从第三个开始到第五个的字符
print(str[2:])             # 输出从第三个开始后的所有字符
print(str[1:5:2])          # 输出从第二个开始到第五个且每隔一个的字符（步长为2）
print(str * 2)             # 输出字符串两次
print(str + '你好')         # 连接字符串
 
print('------------------------------')
 
print('hello\nrunoob')      # 使用反斜杠(\)+n转义特殊字符
print(r'hello\nrunoob')     # 在字符串前面添加一个 r，表示原始字符串，不会发生转义
```


### 空行
函数之间或类的方法之间用空行分隔，表示一段新的代码的开始。    
类和函数入口之间也用一行空行分隔，以突出函数入口的开始。    

空行与代码缩进不同，空行并不是 Python 语法的一部分。    
书写时不插入空行，Python 解释器运行也不会出错。   
但是空行的作用在于分隔两段不同功能或含义的代码，便于日后代码的维护或重构。    

记住：**空行也是程序代码的一部分。**

### 等待用户输入
```python
input("\n\n按下 enter 键后退出。")
```

### 同一行输入多条语句

```py
import sys; x = 'runoob'; sys.stdout.write(x + '\n')
```

### 多个语句构成代码组
缩进相同的一组语句构成一个代码块，我们称之代码组。    
像`if`、`while`、`def`和`class`这样的复合语句，   
首行以关键字开始，以冒号结束，    
该行之后的一行或多行代码构成代码组。    
我们将首行及后面的代码组称为一个子句(clause)。    
```py
if expression : 
   suite
elif expression : 
   suite 
else : 
   suite
```

### print 输出
print 默认输出是换行的，    
如果要实现不换行需要在变量末尾加上 end=""：

```py
x="a"
y="b"
# 换行输出
print( x )
print( y )
 
print('---------')
# 不换行输出
print( x, end=" " )
print( y, end=" " )
print()
```

### import 与 from...import
在 python 用 import 或者 from...import 来导入相应的模块。

将整个模块(somemodule)导入    
格式为： `import somemodule`    

从某个模块中导入某个函数    
格式为： `from somemodule import somefunction`    

从某个模块中导入多个函数    
格式为： `from somemodule import firstfunc, secondfunc, thirdfunc`    

将某个模块中的全部函数导入    
格式为： `from somemodule import *`   
```py
#导入 sys 模块
import sys
print('================Python import mode==========================')
print ('命令行参数为:')
for i in sys.argv:
    print (i)
print ('\n python 路径为',sys.path)

#导入 sys 模块的 argv,path 成员
from sys import argv,path  #  导入特定的成员
 
print('================python from import===================================')
print('path:',path) # 因为已经导入path成员，所以此处引用时不需要加sys.path
```

### 命令行参数
很多程序可以执行一些操作来查看一些基本信息    
Python可以使用-h参数查看各参数帮助信息：

```py
$ python -h
usage: python [option] ... [-c cmd | -m mod | file | -] [arg] ...
Options and arguments (and corresponding environment variables):
-c cmd : program passed in as string (terminates option list)
-d     : debug output from parser (also PYTHONDEBUG=x)
-E     : ignore environment variables (such as PYTHONPATH)
-h     : print this help message and exit

[ etc. ]
```