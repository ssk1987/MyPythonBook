## break 语句

理解：

1.跳出循环体，后面的代码不再执行。

2.可以让while语句的else部分不执行。

概念：

break语句可用于 while 和 for 循环，用来结束整个循环。

当有嵌套循环时，break语句只能跳出最近一层的循环。

---

演示：

```
# 录入过程
while True:
    str_score = input("请输入成绩：")
    if str_score == '':
        break
    list_score.append(int(str_score))

# 输出过程
for item in list_score:
    print(item)

print("最高分：" + str(max(list_score)))
print("最低分：" + str(min(list_score)))
print("平均分：" + str(sum(list_score) / len(list_score)))

```
