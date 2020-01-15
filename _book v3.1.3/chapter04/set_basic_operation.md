# 集合 set

## 1.定义


1.由一系列不重复的不可变类型变量组成的可变映射容器。
2.相当于只有键没有值的字典(键则是集合的数据)。

## 2.基础操作

- 创建空集合：

```
集合名 = set()
集合名 = set(可迭代对象)
```

- 创建具有默认值集合

```
集合名 = {1, 2, 3}
集合名 = set(可迭代对象)
```

- **set --> str**

```
set01 = set("abcac")

list01 = list(set01)

str01 = "".join(list01)

print(str01)  # "bca"
```

## 3.添加元素：

```
集合名.add(元素)
```

## 4.删除元素：

```
集合名.discard(元素)
集合名.remove(元素)
```
演示：

```
set02 = {"a", "b", "a"}

set02.remove("a")
set02.discard("a")
print(set02)
```

## 5.获取集合元素

```
# 获取所有元素
for item in set02:
    print(item)
```




