
## 列表VS字符串


1.列表和字符串都是序列,元素之间有先后顺序关系。

2.字符串是不可变的序列,列表是可变的序列。

3.字符串中每个元素只能存储字符,而列表可以存储任意类型。

4.列表和字符串都是可迭代对象。

5.函数：

将多个字符串拼接为一个。
```
result = "连接符".join(列表)
```
将一个字符串拆分为多个。
```
列表 = “a-b-c-d”.split(“分隔符”)
```
----

- **累加拼接字符串**

缺点：每次循环形成（+=）一个`新的字符串对象`,替换变量引用result。

```
# 需求：根据ｘｘ逻辑，拼接一个字符串.
# "0123456789"

result = ""
for item in range(10):
    #"" 每次循环累加的过程演示
    #"0"
    #"01"
    #"012"
    result = result + str(item)

print(result)   # 0123456789
```

- **join拼接字符串**

优点：每次循环只向列表添加字符串，`没有创建列表对象`。
```
# 建个空列表
list_temp = []
# 循环插入 0-9(需要类型转换 str)
for item in range(10):
    list_temp.append(str(item))

# join : list --> str

# 拼接列表 没有空格的
result = "".join(list_temp)

print(type(result)) # <class 'str'>

print(result)   # 0123456789
```

- **split 拆分**

```
str01 = "张无忌-赵敏-周芷若"

list_result = str01.split("-")

print(list_result)

# ['张无忌', '赵敏', '周芷若']
```
