## 条件表达式

语法：
```
变量 = 结果1 if 条件 else 结果2
```

作用：根据条件(True/False) 来决定返回结果1还是结果2。

----

在选择和循环结构中，条件表达式的值为False的情况如下：

> False、0、0.0、空值None、空序列对象（空列表、空元组、空集合、空字典、空字符串）、空range()对象、空迭代对象、

`其他情况，均为True。`

这么看来，Python所有合法表达式都可以看做条件表达式，甚至包括函数调用的表达式。

演示：
```
# 条件表达式:有选择性的为变量进行赋值
# sex = None
# if input("请输入性别:") == "男":
#     sex = 1
# else:
#     sex = 0
# print(sex)

sex = 1 if input("请输入性别:") == "男" else 0

print(sex)
```


---
### 【操作】测试各种条件表达式
```
if 3:               # 整数作为条件表达式
    print("OK")

a = []              # 列表作为表达式，由于为空列表，是False

if a:
    print("空列表,False")

s = "False"          # 非空字符串，是True

if s:
    print("非空字符串，是True")

c = 9
if 3 < c < 20:
    print("3 < c < 20")

if 3 < c and c < 20:
    print("3 < c and c < 20")

if True:        # 布尔值
    print("True")

# 执行结果
'''
OK
非空字符串，是True
3 < c < 20
3 < c and c < 20
True
'''

```

