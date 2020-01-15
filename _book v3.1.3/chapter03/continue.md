## continue 语句

- 跳过本次，继续下次循环。

- continue语句用于结束本次循环，继续下一次。

- 多个循环嵌套时，continue 也是应用于最近的一层循环。

演示：

```
#　累加1--100之间,能被５整除的数字
# sum_value = 0
# for item in range(1,101):
#     满足条件则累加
#     if item % 5 == 0:
#         sum_value+=item
# print(sum_value)

sum_value = 0
for item in range(1,101):
    # 不满足条件则跳过本次循环,继续下次循环。
    if item % 5 != 0:
        continue
    sum_value+=item
print(sum_value)
```

---
### 【操作】

要求输入员工的薪资，若薪资小于0则重新输入。最后打印出录入员工的数量和薪资明细，以及平均薪资

```
#-*-coding:utf-8-*-

empNum = 0           # 员工数量
salaryNum = 0        # 员工薪资
salarys = []         # 用于存储所有员工工资明细的列表

while True:
    s = input("Please enter the employee's salary (quit by Q or q): ")

    if s.upper() == 'Q':
        print("Success! Quit!")
        break

    if float(s) < 0:
        continue                 # 跳过当前

    empNum += 1                  # 员工数量+1
    salarys.append(float(s))     # 录入到列表中
    salaryNum += float(s)        # 员工工资

print("Number of employees: {0}".format(empNum))
print("Input salary: ", salarys)
print("Average salary: {0}".format(int(salaryNum / empNum)))

# 运行结果
'''
Please enter the employee's salary (quit by Q or q): 12000
Please enter the employee's salary (quit by Q or q): -500
Please enter the employee's salary (quit by Q or q): 600
Please enter the employee's salary (quit by Q or q): 700
Please enter the employee's salary (quit by Q or q): 1588
Please enter the employee's salary (quit by Q or q): 16666
Please enter the employee's salary (quit by Q or q): q
Success! Quit!
Number of employees: 5
Input salary:  [12000.0, 600.0, 700.0, 1588.0, 16666.0]
Average salary: 6310
'''
```
