## range 函数

1.作用:

- 用来创建一个生成一系列整数的可迭代对象(也叫整数序列生成器)。
- range对象是一个迭代器对象，用来产生指定范围的数字序列。

2.语法:
```
range(start, end [, step])
range(开始点，结束点，间隔)
```
3.说明:

> 函数返回的可迭代对象可以用for取出其中的元素

1. 生成数值序列从 start 开始到 end 结束（不包含 end结束点）。

2. 若没有填写 start ,则默认从 0 开始。

3. step 是可选的步长，默认为 1.

----

演示：

```
# 整数生成器:  range(开始值,结束值,间隔)
# for + range ：　更善于执行预定次数。

for item in range(5):#01234
    print(item)
```

##### 如下面几种典型示例：
```
for i in range(10)          # 产生序列：0 1 2 3 4 5 6 7 8 9

for i in range(3, 10)       # 产生序列：3 4 5 6 7 8 9

for i in range(3, 10, 2)    # 产生序列：3 5 7 9
```

```
# # 累加前几个月天数
total_day = 0
for i in range(month - 1):
    total_day += day_of_month[i]
# 累加当月天数
total_day += day
print("是这年的第%d天." % total_day)

# 方法二:
# 累加前几个月天数
total_day = sum(day_of_month[:month - 1])
total_day += day
print("是这年的第%d天." % total_day)
```
