# "魔法"方法

1. 打印id()

如果把BMW使用print进行输出的话，会看到如下的信息

```
# 定义类
class Car:
    # 移动
    def move(self):
        print('车在奔跑...')

    # 鸣笛
    def toot(self):
        print("车在鸣笛...嘟嘟..")


# 创建一个对象，并用变量BMW来保存它的引用
BMW = Car()
BMW.color = '黑色'
BMW.wheelNum = 4 #轮子数量
BMW.move()
BMW.toot()
print(BMW.color)
print(BMW.wheelNum)

print(BMW)
```
运行结果：

![](http://www.python87.com/uploads/allimg/200103/1_2107355391.png)

即看到的是创建出来的BMW对象在内存中的地址

2. 定义`__str__()`方法

```
class Car:

    def __init__(self, newWheelNum, newColor):
        self.wheelNum = newWheelNum
        self.color = newColor

    def __str__(self):
        msg = "嘿。。。我的颜色是{0},我有{1}个轮胎...".format(self.color,int(self.wheelNum))
        return msg

    def move(self):
        print('车在跑，目标:夏威夷')


# 创建一个对象，并用变量BMW来保存它的引用

BMW = Car(4, "白色")
print(BMW)
```
运行结果：
```
嘿。。。我的颜色是白色,我有4个轮胎...
```

### 总结


- 在python中方法名如果是`__xxxx__()`的，那么就有特殊的功能，因此叫做“魔法”方法

- 当使用print输出对象的时候，只要自己定义了`__str__(self)`方法，那么就会打印从在这个方法中return的数据




