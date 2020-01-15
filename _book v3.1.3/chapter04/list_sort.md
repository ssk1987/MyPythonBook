# 列表排序(冒泡排序)

## 列表升序排列

- 思想

```
# 列表排序(升序小　-->  大)
# [3,80,45,5,7,1]
# 目标:列表中所有元素两两比较
# 思想:
# 　取出第一个元素,与后面元素进行比较.
# 　取出第二个元素,与后面元素进行比较.
# 　取出第三个元素,与后面元素进行比较.
#   ...
#   取出倒数第二个元素,与后面元素进行比较.
#   如果取出的元素大于(>)后面的元素,
#       则交换
```

- 思路代码：

```
# 取出第一个元素,与后面元素进行比较
# list01[0]  list01[1]
# list01[0]  list01[2]
# list01[0]  list01[3]

# for c in range(1,len(list01)):
#     # list01[0]  list01[c]
#     pass

# 取出第二个元素,与后面元素进行比较
# for c in range(2,len(list01)):
#     # list01[1]  list01[c]
#     pass

# 取出第三个元素,与后面元素进行比较
# for c in range(3,len(list01)):
#     # list01[2]  list01[c]
#     pass
# 取数据
```

- 实现代码：

```
list01 = [3, 81, 3, 5, 81, 5]

for r in range(len(list01) - 1):
    # 作比较
    for c in range(r + 1, len(list01)):
        # list01[2]  list01[c]
        if list01[r] > list01[c]:
            list01[r], list01[c] = list01[c], list01[r]

print(list01)
```

## 判断列表中元素是否具有相同的

- 思路

```
所有元素俩俩比较,发现相同的则打印结果

所有元素比较结束，都没有发现相同项，则打印结果.
```

- 推导过程

```
# 取出第一个，与后面比较
# list01[0]  list01[1]
# list01[0]  list01[2]
# list01[0]  list01[3]

# for c in range(1,len(list01)):
#     # list01[0]  list01[c]
#     pass

# for c in range(2,len(list01)):
#     # list01[1]  list01[c]
#     pass

# for c in range(3,len(list01)):
#     # list01[2]  list01[c]
#     pass
```

- 实现代码

```
list01 = [3, 81, 3, 5, 81, 5]

# 结果：假设没有相同项
result = False
for r in range(0, len(list01) - 1):
    for c in range(r + 1, len(list01)):
        if list01[r] == list01[c]:
            print("具有相同项")
            result = True
            break  # 退出循环
    if result:
        break

if result == False:
    print("没有相同项")
```















1
