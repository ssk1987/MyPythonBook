# 元组基础操作

## 1·定义


1.由一系列变量组成的不可变序列容器。

2.不可变是指一但创建，不可以再添加/删除/修改元素。

## 2.基础操作

- 创建空元组

```
元组名 = ()
元组名 = tuple()
```

- 创建非空元组

> 注意：创建只有一个元素的元组时,元素后需要加`逗号 ,`

```
元组名 = (20,) # 只有一个元素的元组

元组名 = (1, 2, 3)
元组名 = 100,200,300
元组名 = tuple(可迭代对象)
```

- 获取元素 ( 根据 索引、切片 )

```
tuple03 = ("a", "b", "c", "d")
e01 = tuple03[1]
print(type(e01))  # str

e02 = tuple03[-2:]
print(type(e02))  # tuple
```

- 元组属于不可变序列(容器)

```
tuple01 = (1, 2, 3, 4, 5, 6)

tuple01[0] = 10

print(tuple01)

# 报错信息
# TypeError: 'tuple' object does not support item assignment
```

- 可以直接将元组赋值给多个变量

```
tuper04 = (100, 200)

a, b = tuper04

print(a)
print(b)
```

- 遍历元组：

> Python 有反向索引

```
	正向：
	for 变量名 in 列表名:
		变量名就是元素

	反向：
	for 索引名 in range(len(列表名)-1,-1,-1):
		元祖名[索引名]就是元素
```

- 列表转元组

```
tuple01 = tuple(["a", "b"])
print(tuple01)
```

- 元组转列表

```
list01 = list(tuple01)
print(list01)
```
