# 应用

目标

综合使用 if 语句的相关知识

---
#### 猜拳游戏


演示图：

![](http://www.python87.com/uploads/allimg/200103/1_2155477321.png)

参考代码：
```
# 引入随机数模块
import random

player = input('请输入：剪刀(0)  石头(1)  布(2):')

player = int(player)

computer = random.randint(0, 2)

# 用来进行测试
# print('player=%d,computer=%d',(player,computer))

if ((player == 0) and (computer == 2)) or ((player == 1) and (computer == 0)) or ((player == 2) and (computer == 1)):
    print('获胜，哈哈，你太厉害了')
elif player == computer:
    print('平局，要不再来一局')
else:
    print('输了，不要走，洗洗手接着来，决战到天亮')
```
-----

#### 猜数字2.0


最多猜３次，如果猜对提示"猜对了，总共猜了?次"

如果超过次数，提示"游戏结束".

参考代码：

```
import random

random_number = random.randint(1, 100)
print(random_number)
count = 0
while count < 3:
    # 三次以内
    count += 1
    input_number = int(input("请输入数字："))
    if input_number > random_number:
        print("大了")
    elif input_number < random_number:
        print("小了")
    else:
        print("猜对了，总共猜了" + str(count) + "次")
        break# 退出循环体，不会执行else语句。
else:# while的条件不满足
    # 三次以外
    print("失败")
```
