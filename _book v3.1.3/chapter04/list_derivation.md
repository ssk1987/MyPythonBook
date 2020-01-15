
# 列表推导式


## 1.定义：

使用简易方法，将可迭代对象转换为列表。

## 2.语法：
```
变量 = [表达式 for 变量 in 可迭代对象]
变量 = [表达式 for 变量 in 可迭代对象 if 条件]
```
## 3.说明:

如果if真值表达式的布尔值为False,则可迭代对象生成的数据将被丢弃。

---

## 4.演示：

- 将list01中所有元素,增加１以后存入list02中.

```
list01 = [5, 56, 6, 7, 7, 8, 19]

list02 = []

# 正常写法
for item in list01:
    list02.append(item + 1)

# 列表推导式写法
list02 = [item + 1 for item in list01]

print(list02)
```

- 将list01中大于１０元素,增加１以后存入list02中.

```
list02 = []

# 正常写法
for item in list01:
    if item > 10:
        list02.append(item + 1)

# 列表推导式写法
list02 = [item + 1 for item in list01 if item > 10]

```

## 5.练习题：传统写法 --> 推导式


```
题目：

# 练习:使用range生成1--10之间的数字,将数字的平方存入list01中
# 将list01中所有奇数存入list02
# 将list01中所有偶数存入list03
# 将list01中所有偶数大于5的数字增加1后存入list04
```

**参考推导代码：**

**Test.1**

```
# 传统写法
list01 = []
for item in range(1, 11):
    list01.append(item ** 2)

# 推导式写法
list01 = [item ** 2 for item in range(1, 11)]
```

**Test.2**

```
# 传统写法
list02 = []
for item in list01:
    if item % 2 == 1:
        list02.append(item)

# 推导式写法
list02 = [item for item in list01 if item % 2 == 1]

# 换个条件又变成相反的结果
list03 = [item for item in list01 if item % 2 == 0]
```

**Test.3**

```
# 传统写法
list04 = []
for item in list01:
    if item % 2 == 0 and item > 5:
        list04.append(item + 1)

# 推导式写法
list04 = [item + 1 for item in list01 if item % 2 == 0 and item > 5]
```

**Test.4**

```
题目：将1970年到2050年中的闰年，存入列表．

# 传统写法
list_result = []
for item in range(1970, 2051):
    if item % 4 == 0 and item % 100 != 0 or item % 400 == 0:
        list_result.append(item)
print(list_result)

# 推导式写法
list_result = [item for item in range(1970, 2051) if item % 4 == 0 and item % 100 != 0 or item % 400 == 0]

print(list_result)
```



