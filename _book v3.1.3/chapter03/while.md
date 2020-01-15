# while 循环语句

## 1.作用:

可以让一段代码满足条件，重复执行。

循环结构用来重复执行一条或多条语句。

```
while循环适合根据条件循环执行
```

**表达这样的逻辑**：如果符合条件，则反复执行循环体里的语句。在每次执行完后都会判断一次条件是否为True，如果为True则重复执行循环体里的语句。

## **2.图示**：

![](http://www.python87.com/uploads/allimg/190829/1-1ZRZS320F9.jpg)


## 3.语法:
```
    while 条件:
        满足条件执行的语句
    else:
        不满足条件执行的语句
```

## 4.说明:

else子句可以省略。

在循环体内用break终止循环时,else子句不执行。

> 【提醒】循环体里面的语句_至少应该包含改变条件表达式的语句_，以使循环趋于结束；否则，就会变成一个死循环。

----

## 5.演示：

```
# 需求:执行三次

count = 0
while count < 3:  # 0  1  2
    count += 1
    usd = int(input("请输入美元："))
    print(usd * 6.9)
```

---

## 6.练习题演示：

```
"""
练习:在控制台中循环录入商品信息(名称,单价).
    如果名称输入空字符,则停止录入.
    将所有信息逐行打印出来.
"""
dict_commodity_info = {}

while True:
    name = input("请输入商品名称：")
    if name == "":
        break
    price = int(input("请输入商品单价："))
    dict_commodity_info[name] = price

for key,value in dict_commodity_info.items():
    print("%s商品单价是%d"%(key,value))
```
