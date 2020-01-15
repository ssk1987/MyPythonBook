# 形参定义方式parameter

## 1.缺省参数

- 语法：

```
def 函数名(形参名1=默认实参1, 形参名2=默认实参2, ...):
      函数体
```
- 说明：

缺省参数必须自右至左依次存在，如果一个参数有缺省参数，则其右侧的所有参数都必须有缺省参数。

缺省参数可以有0个或多个，甚至全部都有缺省参数。

## 2.位置形参

- 语法：

```
def 函数名(形参名1, 形参名2, ...):
    函数体
```

## 3.星号元组形参

- 语法：

```
def 函数名(*元组形参名):
    函数体
```

- 作用：

收集多余的位置传参。

- 说明：

> 一般命名为'args'

形参列表中最多只能有一个,`*args`将所有实参合并为一个元组，`作用：让实参个数无限。`

## Exercise:

```
def fun(*args):
    print(args)

fun()
fun(1)
fun(1,"2")
fun(*[1,2,3,"d"])
fun([1,2,3,"d"])
```

```
# 定义一个函数，数值相加的函数
# 所以传入多少个实参，都能够计算

def sum_number(*args):
    result=0
    for i in args:
        result+=i
    return result

result=sum_number(1,2,3,4,5)

print(result)

```

## 4.命名关键字形参

- 语法：

```
def 函数名(*, 命名关键字形参1, 命名关键字形参2, ...):
    函数体

def 函数名(*args, 命名关键字形参1, 命名关键字形参2, ...):
    函数体
```
- 作用：

强制实参使用关键字传参

## 5.双星号字典形参

- 语法：

```
def 函数名(**字典形参名):
    函数体
```

- 作用：

收集多余的关键字传参

- 说明:

> 一般命名为'kwargs'

形参列表中最多只能有一个

### 参数自左至右的顺序

> 位置形参 --> 星号元组形参 --> 命名关键字形参 --> 双星号字典形参

## 6.演示

```
# 1. 缺省(默认)形参:如果实参不提供，可以使用默认值.
def fun01(a=None, b=0, c=0, d=0):
    print(a)
    print(b)
    print(c)
    print(d)

# 关键字实参 + 缺省形参:调用者可以随意传递参数.
# fun01(b=2, c=3)

# 2. 位置形参
def fun02(a, b, c, d):
    print(a)
    print(b)
    print(c)
    print(d)

# 3.星号元组形参: * 将所有实参合并为一个元组
# 作用：让实参个数无限
def fun03(*args):
    print(args)

# fun03()# ()
# fun03(1)# (1,)
# fun03(1,"2")# (1, '2')

# 4.命名关键字形参:在星号元组形参以后的位置形参
# 目的：要求实参必须使用关键字实参.
def fun04(a, *args, b):
    print(a)
    print(args)
    print(b)

fun04(1, b=2)
fun04(1, 2, 3, 4, b=2)

def fun05(*, a, b):
    print(a)
    print(b)

fun05(a=1, b=2)

# 5. 双星号字典形参：**目的是将实参合并为字典.
#               实参可以传递数量无限的关键字实参.
def fun06(**kwargs):
    print(kwargs)

fun06(a=1, b=2)

# 作业:调用fun07。
def fun07(a, b, *args, c, d, **kwargs):
    pass

```

## 7.作业:调用fun07 代码

```
#      ｜位置｜｜星号元组｜｜命名关键字｜｜双星号字典｜
def fun07(a, b, *args, c, d, **kwargs):
    print(a)
    print(b)
    print(args)
    print(c)
    print(d)
    print(kwargs)

fun07(1, 2, 3, 4, 5, c=6, d=7, e=8, f=9)

# 位置实参无限　＋　关键字实参无限
def fun01(*args, **kwargs):
    print(args)
    print(kwargs)


fun01(1, 2, 3, a=4, c=5)
```
