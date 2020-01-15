# 函数内存图分析

## 相关代码 及 内存图

![函数内存图1](http://www.python87.com/uploads/allimg/200104/1_2148184891.jpg)

```
# 在方法区中存储函数代码,不执行函数体
def fun01(a):
    a = 100

num01 = 1
# 因为调用函数，所以开辟一块内存空间，叫做栈帧
# 用于存储在函数内部定义的变量(包含参数).
fun01(num01)
# 函数执行完毕后，栈帧立即释放(其中定义的变量也会销毁).
print(num01)  # 1
```

----

![函数内存图2](http://www.python87.com/uploads/allimg/200104/1_2148183762.jpg)


```
def fun02(a):
    # 改变的是传入的可变对象
    a[0] = 100


list01 = [1]
fun02(list01)
print(list01[0])  # 100
```

-------

![函数内存图3](http://www.python87.com/uploads/allimg/200104/1_2148183533.jpg)

```
def fun03(a):
    # 改变的是fun03栈帧中变量a的指向
    a = 100


list01 = [1]
fun03(list01)
print(list01[0])  # 1
```
----

![函数内存图4](http://www.python87.com/uploads/allimg/200104/1_2148184194.jpg)

```
def fun04(a):
    a[1] = [200]


list01 = [1, [2, 3]]
fun04(list01)
print(list01[1])  # [200]
```

----

![全局变量内存图](http://www.python87.com/uploads/allimg/200104/1_2148181525.jpg)

```
# 全局变量
g01 = "ok"

# print(l01)
def fun01():
    # 局部变量：在函数内部定义的变量
    l01 = 100
    # print(l01)
    print(l01)
    # 　在函数内部可以读取全局变量
    # print(g01)

    # 创建了一个局部变量g01，而不是修改全局变量
    # g01 = "no"

    # 定义全局变量g01
    global g01
    # 此时修改的是全局变量
    g01 = "no"
    print(g01)
    # 定义全局变量g02
    global g02
    g02 = 250

fun01()

print(g01)  # ?

print(g02)
```



