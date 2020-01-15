# for 循环语句

## 1.作用:

> 用来遍历可迭代对象的数据元素。

可迭代对象是指能依次获取数据元素的对象，例如：容器类型。

```
【重点】

while 循环适合 根据条件 循环执行
for   循环适合 执行预定次数 的循环
```

## 2.语法:

```
    for 变量列表 in 可迭代对象:
        语句块1
    else:
        语句块2
```

## 3.说明:

else子句可以省略。

在循环体内用`break`终止循环时,else子句不执行。


## 4.for循环嵌套

```
结论：外层循环执行一次，内层循环执行多次。
      外层控制行，内层控制列.
```

Test01:

```
# 外层循环控制行
for r in range(3):#       0    1     2
    # 内层循环控制列
    for c in range(4):# 0123  0123  0123
        print("*",end = " ")
    print()

"""
    *#*#*#
    *#*#*#
    *#*#*#
    *#*#*#
"""
```

Test02:

```
for r in range(4):
    for c in range(6):
        if c % 2 ==0:
            print("*", end = " ")
        else:
            print("#", end = " ")
    print()

"""
* # * # * #
* # * # * #
* # * # * #
* # * # * #
"""


"""    外层4　　　　内层
    *              0
    **             01
    ***            012
    ****           0123
"""
*
**
***
****
```

----

演示：

```
str01 = "我叫苏大强!"

# item 存储的是字符串中每个字符的地址
for item in str01:
    print(id(item))

# 需求：折纸１０次
thickness = 0.0001
for item in range(10):
    thickness*=2
print(thickness)
```