
## 定义


由一系列变量组成的可变序列容器。

## 基础操作


1.创建列表：
```
列表名 = []
列表名 = list(可迭代对象)
```
演示：

```
# 创建空列表

list01 = []
list01 = list()

# 创建有默认值列表

list02 = ["悟空", 100, True]
list02 = list("我是齐天大圣")
```
执行结果：

```
['悟空', 100, True]
['我', '是', '齐', '天', '大', '圣']
```
---

2.获取元素

```
# 索引
print(list02[2])  # 齐

# 切片
print(list02[-4:])  # ['齐', '天', '大', '圣']
```

---

3.添加元素：
```
列表名.append(元素)
列表.insert(索引，元素)

# 追加(在末尾添加)
list02.append("八戒")

# 插入(在指定位置添加)
list02.insert(1, True)
# 在索引为１(第二个)的位置添加True
```

4.定位元素：

`目的：可以增删改查元素`

```
索引、切片

# 切片
del list02[1:3]
print(list02)
# [True, '大', '圣', '八戒']
# [True, 'a', 'b', '八戒']

list02[1:3] = ["a", "b"]
# [True,'八戒']
# list02[1:3] = []
print(list02)
```

5.遍历列表：
```
正向：
	for 变量名 in 列表名:
		变量名就是元素

反向：
	for 索引名 in range(len(列表名)-1,-1,-1):
		列表名[索引名]就是元素
```

演示：
```
# 获取列表中所有元素
for item in list02:
    print(item)

# 倒序获取所有元素
# 不建议
# list02[::-1] 通过切片拿元素，会重新创建新列表.
# for item in list02[::-1]:
#     print(item)

# 3  2  1  0
for i in range(len(list02) - 1, -1, -1):
    print(list02[i])

# -1  -2  -3  -4
for i in range(-1, -len(list02) - 1, -1):
    print(list02[i])
```

---

6.删除元素：
```
列表名.remove(元素)
del 列表名[索引或切片]

# 根据元素删除
list02.remove("是")

# 根据位置删除
del list02[0]

print(list02)
```
