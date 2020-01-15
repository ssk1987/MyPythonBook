# 列表推导式嵌套

## 1.语法：
```
变量 = [表达式 for 变量1 in 可迭代对象1 for 变量2 in可迭代对象2]
```

## 2.传统写法：

```
result = []
for r in  ["a", "b", "c"]:
    for c in ["A", "B", "C"]:
        result.append(r + c)
```

## 3.推导式写法：

```
result = [r + c for r in list01 for c in list02]
```

## 4.演示：

```
list01 = ["a", "b", "c"]
list02 = ["A", "B", "C"]

result = [r + c for r in list01 for c in list02]

print(result)

# 执行结果
# ['aA', 'aB', 'aC', 'bA', 'bB', 'bC', 'cA', 'cB', 'cC']
```

----

## 5.列表嵌套字典

```
[
    {"name":"张无忌","age":28,"score":100,"sex":"男"},
]
```

参考代码

```
list_student_info = []
while True:
    name = input("请输入姓名：")
    if name == "":
        break
    age = int(input("请输入年龄："))
    score = int(input("请输入成绩："))
    sex = input("请输入性别：")
    dict_info = {"name": name, "age": age, "score": score, "sex": sex}
    list_student_info.append(dict_info)

for dict_info in list_student_info:
    print("%s的年龄是%d,成绩是%d,性别是%s" % (dict_info["name"], dict_info["age"], dict_info["score"], dict_info["sex"]))
# 获取第一个学生信息
dict_info = list_student_info[0]
print("第一个录入的是：%s,年龄是%d,成绩是%d,性别是%s" % (dict_info["name"], dict_info["age"], dict_info["score"], dict_info["sex"]))

```

