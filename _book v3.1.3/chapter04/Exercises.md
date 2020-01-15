# 容器相关练习题


练习:在控制台中录入多个人的多个喜好,输入空字符停止.

```
例如:请输入姓名：
    请输入第1个喜好：
    请输入第2个喜好：
    ...
    请输入姓名：
    ...
   最后在控制台打印所有人的所有喜好.
[
    {“无忌”:[赵敏,周芷若,小赵]}
]
```

参考代码：

```
list_person_bobby = []
while True:
    name = input("请输入姓名：")
    if name == "":
        break
    dict_person = {name:[]}
    list_person_bobby.append(dict_person)
    while True:
        bobby = input("请输入喜好：")
        if bobby == "":
            break
        dict_person[name].append(bobby)

print(list_person_bobby)
```

执行结果：
```
[{'张三': ['喜欢美女', '喜欢吃肉']}, {'李四': ['喜欢打架', '喜欢惹事']}, {'王五': ['喜欢牌九']}]
```
---

- 使用 字典嵌套列表的方式

```
{
    “无忌”:[赵敏,周芷若,小赵]
}
"""
dict_person_bobby = {}
while True:
    name = input("请输入姓名：")
    if name == "":
        break
    dict_person_bobby[name] = []
    while True:
        bobby = input("请输入喜好：")
        if bobby == "":
            break
        dict_person_bobby[name].append(bobby)

for name, list_bobby in dict_person_bobby.items():
    print("%s喜欢：" % name)
    for item in list_bobby:
        print(item)
```

- 练习:列表的全排列

```
# [“香蕉”,"苹果","哈密瓜"]
# [“可乐”,"牛奶"]

list01 = ["香蕉","苹果","哈密瓜"]
list02 = ["可乐","牛奶"]

# 传统写法
list03 = []
for r in list01:
    for c in list02:
        list03.append(r+c)

# 推导式写法
list04 = [r+c for r in list01 for c in list02]

print(list03)
print(list04)
```

Test.1
```
# 练习1:["无忌","赵敏","周芷若"]
# #   ->{"无忌":2,"赵敏":2,"周芷若":3}
list01 = ["无忌", "赵敏", "周芷若"]
dict01 = {}
for item in list01:
    dict01[item] = len(item)

dict02 = {item: len(item) for item in list01}

print(dict01)
print(dict02)
```

Test.2

```
# 练习2:["无忌","赵敏","周芷若"]  [101,102,103]
#  {"无忌":101,"赵敏":102,"周芷若":103}
# 10:18
list01 = ["无忌", "赵敏", "周芷若"]
list02 = [101, 101, 103]
dict01 = {}
# 通过索引同时在多个列表中获取元素
for i in range(len(list01)):
    # key = list01[i]
    # value = list02[i]
    # dict01[key] = value
    dict01[list01[i]] = list02[i]

print(dict01)
```

Test.3




Test.4




Test.5



Test.6



Test.7



Test.1




Test.1



Test.1



Test.1




Test.1




Test.1




Test.1




Test.1


