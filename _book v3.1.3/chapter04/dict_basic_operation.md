# 字典 dict


## 1.定义


1.由一系列键值对组成的可变映射容器。

2.映射：一对一的对应关系，且每条记录无序。

3.键必须惟一且不可变(字符串/数字/元组)，值没有限制。

## 2.基础操作

- 创建空字典

```
dict01 = {}
dict01 = dict()
```

- 创建具有默认值的字典

```
字典名 = {键1：值1，键2：值2}
字典名 = dict (可迭代对象)

dict01 = {"wj":100,"zm":80,"zr":90}
dict01 = dict([("a","b"),("c","d")])
```

- 获取元素 / 元素查找 ( 根据`key`查找`value` )

```
变量 = 字典名[键]  # 没有键则错误
```

```
# 【注意】如果Key不存在，查找时会报错误.
dict01 = {"wj":100,"zm":80,"zr":90}
print(dict01["qtx"])

# 报错信息： KeyError: 'qtx'

#------------------------------------------
# 【推荐】在查找字典时加一个判断

if "qtx" in dict01:# 如果存在key,才打印
    print(dict01["qtx"])
```

- 添加 / 修改元素

```
语法:
    字典名[键] = 数据
说明:
    键不存在，创建记录。
    键存在，修改映射关系。
```

演示：

```
# 修改元素(之前存在key)
dict01["a"] = "BB"

# 添加(之前不存在key)
dict01["e"] = "f"

```

- 删除字典元素

```
del 字典名[键]

dict01 = {'a':1,'b':2,'c':3}

del dict01["a"]

print(dict01)

# 执行结果：{'b': 2, 'c': 3}
```

- 遍历字典

```
语法：
    for 键名 in 字典名:
        字典名[键名]

    for 键名,值名 in 字典名.items():
        语句
```

- 字典如何根据value查找key

```
# 解决方案１:键值互换
dict02 = {value: key for key, value in dict01.items()}
print(dict02)
print(dict02[101])
# 缺点:如果key重复,交换或则丢失数据。
# 如果需要保持所有数据
# [(k,v),]
list02 = [(value, key) for key, value in dict01.items()]
print(list02)
```


-----
演示：

```
dict01 = {'a': 1, 'b': 2, 'c': 3, 'd': 4}

# 获取字典的key
for key in dict01:
    print(key)

# 获取字典中所有元素
for key in dict01:
    print(key)
    print(dict01[key]) # 根据key获取value

# 获取字典中所有value
for value in dict01.values():
    print(value)



# -----------------------------------------------
# 获取键值对key value(元组)
for item in dict01.items():
    print(item)

# 执行结果
('a', 1)
('b', 2)
('c', 3)
('d', 4)
# -----------------------------------------------
# 获取到的元组,可以根据元组的特性来取值
# 下面2种方式，更推荐第二种，一目了然

# NO.1
for item in dict01.items():
    print(item[0])
    print(item[1])

# NO.2
for k,v in dict01.items():
    print(k)
    print(v)

```

