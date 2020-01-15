# 类和对象


![对象内存图](http://www.python87.com/uploads/allimg/200104/1_2222044421.jpg)

代码：

```
# 类
class Wife:
    # 数据成员
    def __init__(self,name,sex):
        # self 是调用当前方法的对象地址
        self.name = name
        self.sex = sex

    # 行为成员
    def play(self):
        """
            一起玩耍
        """
        print(self.name + "玩耍")

# 创建对象,实际在调用__init__方法
w01 = Wife("莉莉","女")# 自动将对象地址传入方法
# 调用对象的行为
w01.play()# 自动将对象地址传入方法
```

总结：

```
    实例方法：操作对象的变量
    类方法：操作类的变量
    静态方法：即不需要操作实例变量也不需要操作类变量.
```
