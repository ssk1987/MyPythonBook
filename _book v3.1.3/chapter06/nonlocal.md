# nonlocal 语句 / 关键字

## 1.作用：

在内层函数修改外层嵌套函数内的变量

## 2.语法

```
nonlocal 变量名1,变量名2, ...
```

## 3.说明

在被嵌套的内函数中进行使用

## 4.演示代码

- **使用nonlocal声明外层局部变量**

```
# 创建一个函数
def outer():
    # 定义一个变量
    outB = 10

    # 创建一个内部函数
    def inner():
        print('调用outB = ', outB)

    # 调用 inner()
    inner()

# 调用 outer()
outer()               # 调用outB =  10
```

- **在嵌套函数内部修改外部函数的局部变量**

```
# 创建一个函数
def outer():
    # 定义一个变量
    outB = 10

    # 创建一个内部函数
    def inner():
        nonlocal outB               # 声明外部函数的局部变量
        print('调用outB = ', outB)
        # 修改变量outB
        outB = 222

    # 调用 inner()
    inner()
    # 打印看看 outB 是否被修改
    print('outer outB = ', outB)

# 调用 outer()
outer()
# 执行结果
'''
调用outB =  10
outer outB =  222
'''
```

- **在嵌套函数内部修改全局变量**

```
# 定义一个全局变量
a = 55
# 创建一个函数
def outer():
    # 定义一个变量
    outB = 10

    # 创建一个内部函数
    def inner():
        nonlocal outB               # 声明外部函数的局部变量
        print('调用outB = ', outB)
        # 修改变量outB
        outB = 222

        global a                    # 声明全局变量
        # 修改变量a的值
        a = 1000

    # 调用 inner()
    inner()
    # 打印看看 outB 是否被修改
    print('outer outB = ', outB)

# 调用 outer()
outer()

# 打印a 看看 a的值是否被修改
print('a = ', a)
# 执行结果
'''
调用outB =  10
outer outB =  222
a =  1000
'''
```

- **外部嵌套作用域**

```
"""
    外部嵌套作用域
"""

def fun01():
    # 是fun01函数的局部作用域
    # 也是fun02函数的外部嵌套作用域
    a = 1

    def fun02():
        b = 2
        # 可以访问外部嵌套作用域变量
        # print(a)
        # 不能修改外部嵌套作用域变量
        # a = 2# 创建了fun02的局部变量
        # print(a)# 2

        nonlocal a# 声明外部嵌套作用域
        a =2
        print(a)# 2

    fun02()
    print(a)# 1

fun01()
```
