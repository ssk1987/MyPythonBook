## 变量

1.定义：关联一个对象的标识符。

2.命名：必须是字母或下划线开头，后跟字母、数字、下划线。

不能使用关键字\(蓝色\)，否则发生语法错误：`SyntaxError: invalid syntax`。

3.建议命名：字母小写，多个单词以下划线隔开。
```
class_name
```
4.赋值：创建一个变量或改变一个变量关联的数据。

5.语法：变量名 = 数据
```
变量名1 = 变量名2 = 数据

变量名1, 变量名2, = 数据1, 数据2

例如：
x = y = 2

x,y = 3,4

更多详细说明，可查看【 Python简介 --- > 赋值 】
```
---

### 说 明


变量名只能包含字母、数字和下划线。

变量名可以字母或下划线打头，但不能是数字打头。

例如变量命`message_1`。但是不能写成`1_message`。

### 变量交换
```
a = input("请输入第一个变量：")
b = input("请输入第二个变量：")

# 版本1 所有语言通用思维
# temp = a
# a = b
# b = temp

# 版本2 数据交换  python
a, b = b, a
print("第一个变量是：" + a)
print("第二个变量是：" + b)
```
---
### 内存图

![](http://www.python87.com/uploads/allimg/200102/1_1821548812.jpg)

```
语义：内存图
变量名：真实内存地址的别名
       见名知意
赋值号：将右边对象的地址复制给左边内存空间。
```

## 变量内存图

![](http://www.python87.com/uploads/allimg/200102/1_1821545623.jpg)

```
name = "张无忌"
print("name id1", id(name))
name = "赵敏"
a01 = a02 = "周芷若"
b01, b02 = "苏大强", "苏明玉"

print(name)
print("name id2", id(name))
print(a01)
print("a01 id", id(a01))
print(a02)
print("a02 id", id(a02))
print(b01)
print("b01 id", id(b01))

print(b02)
print("b02 id", id(b02))
```
执行结果：
```
name id1 4916968
赵敏
name id2 5411760
周芷若
a01 id 4917136
周芷若
a02 id 4917136
苏大强
b01 id 4917192
苏明玉
b02 id 4917248
```
# 变量内存图练习

![](http://www.python87.com/uploads/allimg/200102/1_1821545534.jpg)

内存图演示代码
```
a = 'A'
b = 'B'
a = b

print(a) # B
```

```
a = 'A'
b = 'B'
a = b
b = 'C'

print(a) # B
```
