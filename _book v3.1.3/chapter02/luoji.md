## 逻辑运算符

### 与and

一假俱假,表示并且(都得满足)的关系。

示例:
```
print(True and True)    # True　都得满足条件，结论才满足条件。
print(False and True)   # False
print(True and False)   # False
print(False and False)  # False
```
### 或 or

一真俱真,表示或者(一个满足就行)的关系

示例:
```
print(True or True)    # True
print(False or True)   # True
print(True or False)   # True
print(False or False)  # False
```

### 非 not

表示取反

例如：
```
print(not True)   # 返回False
print(not False)  # 返回True
```

### 短路运算

一但结果确定，后面的语句将不再执行。

练习：
```
# 练习：判断年份是否为闰年。
# 闰年True:年份能被4整除，但是不能被100整除。能被400整除
# 平年 False

year = int(input("请输入年份："))
result = year % 4 == 0 and year % 100 != 0 or year % 400 == 0
print(result)
```
