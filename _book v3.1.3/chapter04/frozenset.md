# 固定集合 frozenset

## 1.定义

不可变的集合。

## 2.作用

固定集合可以作为字典的`键`,还可以作为集合的`值`。

## 3.基础操作

创建固定集合：frozenset(可迭代对象)

## 4.运算

等同于set

---

## 5.演示

```
set01 = frozenset([1, 2, 3, 3, 5])

list02 = list(set01)

print(set01)
print(list02)
```
运行结果：

```
frozenset({1, 2, 3, 5})
[1, 2, 3, 5]
```
