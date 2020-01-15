# 模块导入方法


## 1. import 模块名

- 语法：

```
import 模块名

import 模块名 as 别名
```

- 作用：将某模块整体导入到当前模块中

- 使用：模块名.成员

```
例如：import  module1

本质：使用变量名module1关联模块地址
```

## 2. from 模块名 import 函数名/类名

- 语法：

```
from 模块名 import 成员名[ as 别名1]
```

- 作用：将模块内的一个或多个成员导入到当前模块的作用域中。

```
本质：将指定的成员导入到当前模块作用域中

小心：导入进来的成员不要和当前模块成员名称冲突
```

## 3. from 模块名 import *

- 语法：

```
from 模块名 import *
```

- 作用：将某模块的所有成员导入到当前模块。

```
本质：将指定模块的所有成员导入到当前模块作用域中

模块中以下划线（_）开头的属性，不会被导入，通常称这些成员为隐藏成员（仅适用于方式3）

只是在模块内部使用的成员，可以通过单下划线（_）开头

```

## 4.导入方式演示

```
# 导入方式1
# 本质：使用变量名module01关联模块地址
# import module01
# module01.fun01()
# my02 = module01.MyClass02()
# my02.fun02()

# as 为导入的成员其另外一个名称
import module01 as m01
m01.fun01()
my02 = m01.MyClass02()
my02.fun02()

# 导入方式2
# 本质：将指定的成员导入到当前模块作用域中
# 小心：导入进来的成员不要和当前模块成员名称相同
# from module01 import fun01
# from module01 import MyClass02
#
# def fun01():
#     print("当前模块fun01")
#
# fun01()
# my02 = MyClass02()
# my02.fun02()

# 导入方式3
# 本质：将指定模块的所有成员导入到当前模块作用域中
# 小心：导入进来的成员和其他模块成员冲突
from module01 import *

fun01()
my02 = MyClass02()
my02.fun02()
```



