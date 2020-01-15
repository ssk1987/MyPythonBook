# 字典 VS 列表

1.都是可变容器。

2.获取元素方式不同,列表用索引,字典用键。

3.字典的插入,删除,修改的速度快于列表。

4.列表的存储是有序的,字典的存储是无序的。

---

## 字典嵌套列表

```
{
    "key":[list],
    ...
    "key":[list],
}

例如：

{
    "张三":['喜欢美女','喜欢吃肉','喜欢不穿衣服'],
    ...
    "王五":['喜欢牌九','喜欢帮倒忙','喜欢看书'],
}

```
演示：

```
dict_student_info = {}

while True:
    name = input("请输入姓名：")
    if name == "":
        break
    age = int(input("请输入年龄："))
    score = int(input("请输入成绩："))
    sex = input("请输入性别：")
    dict_student_info[name] = [age, score, sex]

# 打印所有学生信息
for name,list_info in dict_student_info.items():
    print("%s的年龄是%d,成绩是%d,性别是%s"%(name,list_info[0],list_info[1],list_info[2]))
```
