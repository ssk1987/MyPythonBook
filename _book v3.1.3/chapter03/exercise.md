# 相关练习题

> 凡是计算机能通过的代码都是正确的，区别在于逻辑思维是否和人的思维接近（也就是代码简洁，易理解）。

> 以下代码仅供参考( 学的深了,可以尝试优化下列代码 )

练习题：购买商品找零
```
"""
    需求：
        1、录入一个商品的单价
        2、录入一个数量
        3、计算总金额，以及要找的零钱
        4、当钱不够时，需要提示钱不够
        最后需要调试，知道程序的执行过程，以及取值
        断点需要在可能会出错的地方加
"""

price = float(input("请输入商品的单价："))
number = int(input("请输入购买商品的数量："))
money = int(input("请输入您要给的金额："))

# 金额
amount_money = price * number

if money > amount_money:
    print("商品总额为：{0}元，您支付了{1}元，应找您{2}元。欢迎下次光临！".format(amount_money, money, (money - amount_money)))
else:
    print("您给的钱不够，请重新输入！")

```
练习题：季节对应月份
```
"""
    在控制台中获取一个季节
    显示季节对应的月份
"""

# 获取季度
# 需要获取的是字符串，所以就不需要类型转换了
quarter = input("请输入季节(如：春,夏,秋,冬)：")

# 逻辑判断
if quarter == "春":
    print("您输入的季节为{0},对应的月份是1-3月。".format(quarter))
elif quarter == "夏":
    print("您输入的季节为{0},对应的月份是4-6月。".format(quarter))
elif quarter == "秋":
    print("您输入的季节为{0},对应的月份是7-9月。".format(quarter))
elif quarter == "冬":
    print("您输入的季节为{0},对应的月份是10-12月。".format(quarter))
else:
    print("请输入正确的季节(如：春,夏,秋,冬)。")

# 执行结果
"""
请输入季节(如：春,夏,秋,冬)：夏
您输入的季节为夏,对应的月份是4-6月。

请输入季节(如：春,夏,秋,冬)：1
请输入正确的季节(如：春,夏,秋,冬)。
"""
```
练习题：输入年、月，输出本月有多少天。
```
# 练习：
# 输入年、月，输出本月有多少天。

year = int(input('年:'))
month = int(input('月:'))

if (month == 1 or month == 3 or month == 5 or month == 7
        or month == 8 or month == 10 or month == 12):
    print('31天')
elif (month == 4 or month == 6 or month == 9 or month == 11):
    print('30天')
elif month == 2 and ((year % 4 == 0 and year % 100 != 0) or (year % 400 == 0)):
    print('29天')
else:
    print('28天')
```

练习题：简易计算器


```
"""
    在控制台中获取一个数，及一个运算符，再获取一个数
    根据运算符，做运算
    要求：如果运算符不是（+ - × /）则提示运算符有误
"""

# 获取第一个数
num01 = float(input("请输入第一个数："))

# 获取第二个数
num02 = float(input("请输入第二个数："))

# 获取的运算符为字符串
operator = input("请输入一个运算符(如：+ , - , * , /)：")

# 逻辑运算
if operator == "+":
    print("{0} {1} {2} = {3}".format(num01 ,operator, num02, (num01 + num02)))
elif operator == "-":
    print("{0} {1} {2} = {3}".format(num01 ,operator, num02, (num01 - num02)))
elif operator == "*":
    print("{0} {1} {2} = {3}".format(num01 ,operator, num02, (num01 * num02)))
elif operator == "/":
    print("{0} {1} {2} = {3}".format(num01 ,operator, num02, (num01 / num02)))
else:
    print("请输入正确的运算符(如：+ , - , * , /)!!!")

# 执行结果
"""
请输入第一个数：20
请输入第二个数：30
请输入一个运算符(如：+ , - , * , /)：+
20.0 + 30.0 = 50.0

请输入第一个数：5
请输入第二个数：6
请输入一个运算符(如：+ , - , * , /)：d
请输入正确的运算符(如：+ , - , * , /)!!!
"""

```
练习题：比较最大值

```
"""
    在控制台中分别获取四个数
    打印最大的数
"""

# 思路：假设需要获取的四个数是 1 3 5 7
num01 = int(input("请输入第1个数："))
num02 = int(input("请输入第2个数："))
num03 = int(input("请输入第3个数："))
num04 = int(input("请输入第4个数："))

result = num01

if result < num02:
    result = num02

if result < num03:
    result = num03

if result < num04:
    result = num04

print(result)

```
练习题：成绩查询

```
"""
    在控制台录入成绩(0-100)
    判断成绩分类（优秀 良好 中等 及格 不及格 输入有误）
    ★重点：方法有很多种，目前来说，能达到需求即可，至于是否合理及其他逻辑需要后面的知识来填充。
"""

# 获取成绩
# print("欢迎来到成绩查询系统，请按照下列格式输入您的成绩。")
# print("优秀90+ 良好80+ 中等70+ 及格60+ 不及格60-")

result = float(input("请输入您的成绩："))

# 逻辑

if 90 <= result <= 100 :
    print("您的成绩为：优秀")
elif 79 < result < 90:
    print("您的成绩为：良好")
elif 69 < result < 80:
    print("您的成绩为：中等")
elif 59 < result < 70:
    print("您的成绩为：及格")
elif 0 <= result < 60:
    print("您的成绩为：不及格")
else:
    print("您输入的成绩有误，请重新输入。")

```

练习题：获取月份打印天数
```
"""
    在控制台中获取月份
    打印天数  输入有误
    1 3 5 7 8 10 12 ---> 31天
    4 6 9 11 ---> 30天
    2   ---> 28天
"""
# 获取月份
# 不转换就是字符串比较了
month = int(input("请输入月份："))

# 逻辑
if month < 1 or month > 12:
    print("输入有误。")
elif month == 2:
    print("28天")
elif month == 4 or month == 6 or month == 9 or month == 11:
    print("30天")
else:
    print("31天")
```

练习题：判断整数是奇数还是偶数赋值给变量
```
"""
    在控制台中获取一个整数
    如果是偶数则为变量state赋值“偶数”，如果是奇数则赋值“奇数”
"""

number = int(input("请输入一个整数："))

# 中规中矩的写法如下

if number % 2 == 0:
    state = "偶数"
else:
    state = "奇数"
print(state)

# ************************************************************
# 优化写法如下
# 整数中还涉及到0这个数，目前没解决

state ="偶数" if number % 2 == 0 else "奇数"

print(state)
```

练习题：获取一个年份，判断是否闰年，并给变量赋值
```
"""
    在控制台中获取一个年份
    如果是闰年，则给变量day赋值29，否则赋值28
    Day01 - Day02 练习题08 是教大家怎么判断闰年的，可以把代码直接复制过来参考。
"""

year = int(input("请输入一个年份："))

# 代码可读性差，尽管代码很精简
# day = 29 if not year % 4 and year % 100 or not year % 400 else 28

# 建议写的代码

day = 29 if year % 4 == 0 and year % 100 != 0 or year % 400 == 0 else 28

print(day)
```
---

练习题：while循环输出季度月份
```
"""
    在控制台中获取一个季节
    显示季节对应的月份     练习题014可以参考
"""

while True:
    quarter = input("请输入季节(如：春,夏,秋,冬)：")

    # 逻辑判断
    if quarter == "春":
        print("您输入的季节为{0},对应的月份是1-3月。".format(quarter))
    elif quarter == "夏":
        print("您输入的季节为{0},对应的月份是4-6月。".format(quarter))
    elif quarter == "秋":
        print("您输入的季节为{0},对应的月份是7-9月。".format(quarter))
    elif quarter == "冬":
        print("您输入的季节为{0},对应的月份是10-12月。".format(quarter))
    else:
        print("请输入正确的季节(如：春,夏,秋,冬)。")

    # 退出循环
    if input("按e键退出,回车键继续。") == "e":
        break
```

练习题：while循环计数3个小练习
```
"""
    使用while循环做
        练习1：在控制台中输出 0 1 2 3 4 5
        练习2：在控制台中输出 2 3 4 5 6 7
        练习3：在控制台中输出 0 2 4 6
"""
# 练习1
# 计数器
count = 0
while count < 6:
    # 如果这里放count 等于没打印之前 count就自加1了 输出就会变成 1 2 3 4 5
    # count += 1
    print(count)
    count += 1  # 改变结束条件

# ************************************************************
# 练习2：在控制台中输出 2 3 4 5 6 7
count2 = 2
while count2 < 8:
    print(count2)
    count2 += 1

# ************************************************************
# 练习3：在控制台中输出 0 2 4 6
count3 = 0
while count3 < 7:
    if count3 % 2 == 0: # 判断奇数和偶数会用到
        print(count3)
    count3 += 1

# 下面的代码和练习3的输出效果是一样的。
count4 = 0
while count4 <= 6:
    print(count4)
    count4 += 2
```
练习题：获取月份,显示季度
```
"""
    在控制台中获取月份,显示季度,或者提示月份错误.
    方法一：
"""

month = int(input("请输入月份(1-12)："))

if month < 1 or month > 12:
    print("您输入的月份有误。")
elif month == 1 or month == 2 or month == 3:
    print("春天")
elif month == 4 or month == 5 or month == 6:
    print("夏天")
elif month == 7 or month == 8 or month == 9:
    print("秋天")
else:
    print("冬天")

# ****************************************************
"""
    在控制台中获取月份,显示季度,或者提示月份错误.
    方法二：
"""
month = int(input("请输入月份(1-12)："))

if month < 1 or month > 12:
    print("您输入的月份有误。")
elif month >= 10:
    print("冬天")
elif month >= 7:
    print("秋天")
elif month >= 4:
    print("夏天")
else:
    print("春天")
```

练习题：获取年龄打印成年人
```
"""
    在控制台中获取年龄，
    如果小于０岁，打印输入有误
    如果一个人的年龄小于2岁，就打印一条消息，指出他是婴儿。
    如果一个人的年龄为2（含）～13岁，就打印一条消息，指出他是儿童。
    如果一个人的年龄为13（含）～20岁，就打印一条消息，指出他是青少年。
    如果一个人的年龄为20（含）～65岁，就打印一条消息，指出他是成年人。
    如果一个人的年龄超过65（含）岁～150岁，就打印一条消息，指出他是老年人。
    150岁以上，打印"那不可能"
"""

age = int(input("请输入您的年龄："))

if age > 150:
    print("那不可能")
elif age >= 65:
    print("老年人")
elif age >= 20:
    print("成年人")
elif age >= 13:
    print("青少年")
elif age >= 2:
    print("儿童")
elif age >= 0:
    print("儿童")
else:
    print("输入有误")

```
练习题：根据身高体重,参照BMI,返回身体状况
```
"""
    根据身高体重,参照BMI,返回身体状况.
     BMI:用体重千克数除以身高米数的平方得出的数字
     BMI= weight / height ** 2
     中国参考标准
     体重过低BMI<18.5
     正常范围18.5≤BMI<24
     超重24≤BMI<28
     I度肥胖28≤BMI<30
     II度肥胖30≤BMI<40
     Ⅲ度肥胖BMI≥40.0
"""

print("体重以千克为单位，身高以米为单位，请认真输入您的信息！")

height = float(input("请输入您的身高："))

weight = float(input("请输入您的体重："))

bmi = weight / height ** 2

if bmi >= 40:
    print("Ⅲ度肥胖BMI≥40.0")
elif bmi >= 30:
    print("II度肥胖30≤BMI<40")
elif bmi >= 28:
    print("I度肥胖28≤BMI<30")
elif bmi >= 24:
    print("超重24≤BMI<28")
elif bmi >= 18.5:
    print("正常范围18.5≤BMI<24")
elif bmi >= 0:
    print("体重过低BMI<18.5")
else:
    print("别乱输")

```

练习题：获取开始结束值打印中间数
```
"""
    在控制台中获取一个开始值，一个结束值.
    如 开始值 3   结束值 10
    打印 456789
"""

start_value = int(input("请输入一个开始值："))

end_value = int(input("请输入一个结束值："))

# 计数器
count = start_value + 1
while count < end_value:
    print(count)
    count += 1

# *******************************************************
# 方法二：

start_value = int(input("请输入一个开始值："))

end_value = int(input("请输入一个结束值："))

# 可以不要计数器
while start_value < end_value - 1:
    start_value += 1
    print(start_value)

```
练习题：一张纸对折对少次超珠穆朗玛峰
```
"""
    一张纸的厚度为0.01毫米 1m =10 分米 = 100 cm = 1000毫米
    问对折对少次可超过珠穆朗玛峰 8848.43米 = 8848430毫米
    思路 折一次 纸张厚度变化
    1  0.01 x 2 = 0.02
    2  0.02 x 2 = 0.04
    3  0.04 x 2 = 0.08
    ....
"""

# 计数器 对折次数
count = 1

# 纸张厚度
thickness = 0.01

# while 循环里需要计算单位的一致性，如果改成米的话，则前面输出的厚度会出现科学计数法

while thickness < 8848430:
    thickness = thickness * 2   # 这里也可以写成 thickness *= 2 效果是一样的
    count += 1
    print(thickness)
print(count - 1)

# 这里为什么要减去1 呢？ 因为上面计数器默认值为1 所以要减去这一次，同时也要注意 count所放的位置，放在逻辑运算前与放在逻辑运算后自加1的效果是不一样的。
```

练习题：猜数字游戏
```
"""
    猜数字
    随机生成一个数 1-100之间
    让玩家重复猜测 直到猜对为止
    提示 大了 小了  猜对了，总共猜了多少次
"""

# 随机数工具
import random

# 生成一个随机数
random_number = random.randint(1,100)

# 计数器
count = 0
while True:
    user_num = int(input("请输入你所要猜的数字(范围1-100之间：)"))
    count += 1
    if user_num < random_number:
        print("你猜小了。")
    elif user_num > random_number:
        print("你猜大了")
    else:
        print("恭喜你猜对了！！！")
        print("您总共猜了{0}次".format(count))
        break
```
练习题：猜数字游戏2.0
```
"""
    猜数字 2.0
    随机生成一个数 1-100之间
    让玩家重复猜测 只能猜测3次
    提示 大了 小了  猜对了，总共猜了多少次
    猜错了 提示失败
"""

# 随机数工具
import random

# 生成一个随机数
random_number = random.randint(1,100)

print(random_number)

# 计数器
count = 0
while count < 3:
    # 3次以内执行以下代码
    user_num = int(input("请输入你所要猜的数字(范围1-100之间：)"))
    count += 1
    if user_num < random_number:
        print("你猜小了。")
    elif user_num > random_number:
        print("你猜大了")
    else:
        print("恭喜你猜对了！！！")
        print("您总共猜了{0}次".format(count))
        break   # 退出循环体，则不会执行下面的else语句了
else:
    # 3次使用完则执行此段代码，也就是while循环的条件不满足的时候执行
    print("3次机会已用完，游戏结果！")
```
练习题：while根据成绩判断等级2
```
"""
    循环根据成绩判断等级，如果录入空字符串则退出程序
    如果成绩录入次数达到3次，则退出，并提示 成绩错误过多
"""

count = 0

# 逻辑
while count < 3:
    str_score = input("请输入您的成绩：")
    if str_score == "":
        print("您输入了空的字符串，程序退出")
        break
    score = int(str_score)
    if score <=0 or score > 100:
        print("您输入的成绩错误，请重新输入。")
        count += 1
    elif score >= 90:
        print("您的成绩为：优秀")
    elif score >= 80:
        print("您的成绩为：良好")
    elif score >= 70:
        print("您的成绩为：中等")
    elif score >= 60:
        print("您的成绩为：及格")
    else:
        print("您的成绩为：不及格。")
else:
    print("成绩错误过多。")
```

练习题：累加1-100所有数字的和
```
"""
    for
    累加1-100所有数字的和
"""
result = 0
for item in range(1,101):
    result += item

print(result)   # 5050
```
练习题：累加1-100所有偶数的和
```
"""
    累加 1-100 之间偶数之和
"""
# 用于存储累加数的变量
sesult = 0
for item in range(1,101):
    if item % 2 == 0:       # 奇数和 if item % 2 == 1
        sesult += item
print(sesult)   # 2550      奇数 2500


# ******************************************************
# 方法二
sesult1 = 0
for item1 in range(0,101,2):
        sesult1 += item1
        print(item1)
print(sesult1)   # 偶数 2550
```

练习题：累加1-100所有奇数的和

```
"""
    累加 1-100 之间奇数之和
"""
# 用于存储累加数的变量
sesult = 0
for item in range(1,101):
    if item % 2 == 1:
        sesult += item
print(sesult)   # 2500


# ******************************************************
# 方法二
sesult1 = 0
for item1 in range(1,101,2):
        sesult1 += item1
        print(item1)
print(sesult1)   # 2500
```

练习题：累加 10-36 之间数之和
```
"""
    累加 10-36 之间数之和
"""
# 奇数
sesult = 0
for item in range(10,37):
        sesult += item
        print(item)     # 用于调试看看每次输出的数字是多少
print(sesult)   # 621
```
练习题：while循环做随机数加法考试
```
"""
    随机数加法考试
    随机生成2个随机数 0-10之间
    在控制台获取2个数相加的和
    如果用户输入正确得10分，错误不得分
    总共3道题，最后输出得分
"""

import random

# 计数器
count = 0

# 得分 存储 每次答对时累加的分数
score = 0

while count < 3:
    # 生成随机数
    random_num01 = random.randint(1,10)
    random_num02 = random.randint(1,10)
    count += 1
    sum = random_num01 + random_num02
    user_value = int(input("{0} + {1} = ".format(random_num01, random_num02)))
    if user_value == sum:
        print("恭喜你答对了+10分")
        score += 10
    else:
        print("你答错了")

print("考试结束,您的总得分为：{0} 分".format(score))

# 还可以扩展一个根据分数，判断等级的显示。
```
练习题：for循环做随机数加法考试
```
"""
    随机数加法考试
    随机生成2个随机数 0-10之间
    在控制台获取2个数相加的和
    如果用户输入正确得10分，错误不得分
    总共3道题，最后输出得分
"""
import random
count = 0
# 得分
score = 0
for item in range(3):
    # 生成随机数
    random_num01 = random.randint(1,10)
    random_num02 = random.randint(1,10)
    count += 1
    sum = random_num01 + random_num02
    user_value = int(input("{0} + {1} = ".format(random_num01, random_num02)))
    if user_value == sum:
        print("恭喜你答对了+10分")
        score += 10
    else:
        print("你答错了")

print("考试结束,您的总得分为：{0} 分".format(score))

# 还可以扩展一个根据分数，判断等级的显示。
```
练习题：判断一个数是否为素数
```
"""
    在控制台中获取一个整数，判断是否为素数
    素数：只能被1和自身整除的整数
    思路：排除法，使用2-当前数字之间的整数判断，如果存在被整除则不是素数
    2 3 5 7 11 13 17 19 23
"""
# 获取一个整数
num = int(input("请输入一个整数："))
# 没有判断2以下数字
for item in range(2,num):
    if num % item == 0:
        print("不是素数")
        break
    elif num % (item + 1) == 0:
        print("不是素数")
        break
else:
    print("是素数")
```
练习题：计算 10-50之间 个位不是 2 5 9 的整数之和
```
"""
    计算 10-50之间 个位不是 2 5 9 的整数之和
"""
sum_value = 0

for item in range(10,51):
    if item % 10 == 2:  # 也可以这样写 item % 10 == 2 or item % 10 == 2 or item % 10 == 2
        continue
    elif item % 10 == 5:
        continue
    elif item % 10 == 9:
        continue
    sum_value += item
print(sum_value)
```
练习题:字符和编码值互转操作
```
# 练习1:在控制台中获取一个字符串，循环打印每个字符的编码值

str_value = input("请输入一个字符换:")

for item in str_value:
    print(ord(item))

# 练习2：在控制台中重复录入一个编码值，然后打印字符，如果输入空字符，则退出

while True:
    str_value = input("请输入一个编码值：")
    chr_value = int(str_value)
    if str_value == "":
        break
    else:
        print(chr(chr_value))
```






