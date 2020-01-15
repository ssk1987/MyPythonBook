# 封装

## 1.定义

- 数据角度讲，将一些基本数据类型复合成一个自定义类型。

- 行为角度讲，向类外提供必要的功能，隐藏实现的细节。

- 设计角度讲：

   - (1) 分而治之

   -  -- 将一个大的需求分解为许多类，每个类处理一个独立的功能。

   -  -- 拆分好处：便于分工，便于复用，可扩展性强。

   - (2) 变则疏之

   - -- 变化的地方独立封装，避免影响其他类。

   -  (3) 高 内 聚

   - -- 类中各个方法都在完成一项任务(单一职责的类)。

   - (4) 低 耦 合

   - -- 类与类的关联性与依赖度要低(每个类独立)，让一个类的改变，尽少影响其他类。

[例如：硬件高度集成化，又要可插拔]

最高的内聚莫过于类中仅包含1个方法，将会导致高内聚高耦合。

最低的耦合莫过于类中包含所有方法，将会导致低耦合低内聚。

## 2.作用

1.简化编程，使用者不必了解具体的实现细节，只需要调用对外提供的功能。

2.松散耦合，降低了程序各部分之间的依赖性。

数据和操作相关联，方法操作的是自己的数据。

## 3.私有成员

1.作用：无需向类外提供的成员，可以通过私有化进行屏蔽。

2.做法：命名使用双下划线开头。

3.`本质：障眼法，实际也可以访问` `实际将变量名改为：_类名__变量名`。

私有成员的名称被修改为：_类名__成员名，可以通过_dict_属性或dir函数查看。

## 4.\_\_slots__

- 作用：限定一个类创建的实例只能有固定的实例变量，不能再额外添加。

- 语法：

```
# 在类中定义

__slots__ = (“变量名1”,”变量名2”…..)
```

- 说明：含有 \_\_slots\_\_ 属性的类所创建的对象没有\_\_dict__ 属性, 即此实例不用字典来存储对象的实例属性。

- 优点：访止用户因错写属性的名称而发生程序错误。

- 缺点：丧失了动态语言可以在运行时为对象添加变量的灵活性。

## 5.属性@property

公开的实例变量，缺少逻辑验证。私有的实例变量与两个公开的方法相结合，又使调用者的操作略显复杂。而属性可以将两个方法的使用方式像操作变量一样方便。

- 定义：

```
    @property
    def name(self):
        return self.__name

    @name.setter
    def name(self, name):
        self.__name = name
```

- 调用：

> 对象.属性名 = 数据

> 变量 = 对象.属性名

- 说明：


> -- 通常两个公开的属性，保护一个私有的变量。

> -- @property 负责读取，@属性名.setter 负责写入

> -- 只写：属性名= property(None, 写入方法名)
>

- 演示封装推导过程

**NO.1 使用方法，封装变量**

```
class Wife:
    def __init__(self, name, age, weight):
        self.name = name
        # 本质:障眼法(实际将变量名改为：_类名__age)
        # self.__age = age
        self.set_age(age)
        # self.__weight = weight
        self.set_weight(weight)

    # 提供公开的读写方法
    def get_age(self):
        return self.__age

    def set_age(self, value):
        if 21 <= value <= 31:
            self.__age = value
        else:
            raise ValueError("我不要")

    # 提供公开的读写方法
    def get_weight(self):
        return self.__weight

    def set_weight(self, value):
        if 40 <= value <= 60:
            self.__weight = value
        else:
            raise ValueError("我不要")

"""
w01 = Wife("铁锤公主", 87, 87)
# 重新创建了新实例变量(没有改变类中定义的__age)
# w01.__age = 107
w01._Wife__age = 107  # (修改了类中定义的私有变量)

print(w01.__dict__)# python内置变量,存储对象的实例变量.
"""

w01 = Wife("铁锤公主", 30, 50)
w01.set_age(25)
w01.set_weight(55)
print(w01.get_age())
print(w01.get_weight())
```


**NO.2 使用property(读取方法，写入方法)对象,封装变量.**

```
class Wife:
    def __init__(self, name, age, weight):
        self.name = name
        # self.set_age(age)
        self.age = age
        # self.set_weight(weight)
        self.weight = weight

    def get_age(self):
        return self.__age

    def set_age(self, value):
        if 21 <= value <= 31:
            self.__age = value
        else:
            raise ValueError("我不要")

    # 属性  property对象拦截对age类变量的读写操作
    age = property(get_age,set_age)

    def get_weight(self):
        return self.__weight

    def set_weight(self, value):
        if 40 <= value <= 60:
            self.__weight = value
        else:
            raise ValueError("我不要")

    weight = property(get_weight,set_weight)

w01 = Wife("铁锤公主", 30, 50)
# w01.set_age(25)
w01.age = 25
print(w01.age)
w01.weight = 45
print(w01.weight)

```

**NO.3 使用标准属性,封装变量.**

```
class Wife:
    def __init__(self, name, age, weight):
        self.name = name
        self.age = age
        self.weight = weight

    @property  # 创建property对象，只负责拦截读取操作
    def age(self):
        return self.__age

    @age.setter  # 只负责拦截写入操作
    def age(self, value):
        if 21 <= value <= 31:
            self.__age = value
        else:
            raise ValueError("我不要")

    @property
    def weight(self):
        return self.__weight

    @weight.setter
    def weight(self, value):
        if 40 <= value <= 60:
            self.__weight = value
        else:
            raise ValueError("我不要")

w01 = Wife("铁锤公主", 30, 50)
w01.age = 25
print(w01.age)
w01.weight = 45
print(w01.weight)
```

## 6.封装设计思想

> 需求：老张开车去东北

```
class Person:
    def __init__(self, name):
        self.name = name

    @property
    def name(self):
        return self.__name

    @name.setter
    def name(self, value):
        self.__name = value

    def go_to(self, str_postion, type):
        """
            去
        :param str_postion: 位置
        :param type: 方式
        """
        print(self.name, "去", str_postion)
        type.run(str_postion)

class Car:
    def run(self, str_position):
        """
            行驶
        :param str_position: 位置
        """
        print("汽车行驶到:", str_position)

lz = Person("老张")
car = Car()
# 老张开车去东北
lz.go_to("东北", car)
```

## 8.向对象的思想描述场景

> 请以面向对象的思想，描述下列场景:

> 小明在招商银行取钱

```
class Person:
    def __init__(self, name, money):
        self.name = name
        self.money = money

    @property
    def name(self):
        return self.__name

    @name.setter
    def name(self, value):
        self.__name = value

    @property
    def money(self):
        return self.__money

    @money.setter
    def money(self, value):
        self.__money = value


class Bank:
    def __init__(self, name, money):
        self.name = name
        self.money = money

    @property
    def name(self):
        return self.__name

    @name.setter
    def name(self, value):
        self.__name = value

    @property
    def money(self):
        return self.__money

    @money.setter
    def money(self, value):
        self.__money = value

    def draw_money(self, person, value):
        """
            取钱
        :param person:
        :param value:
        :return:
        """
        self.money -= value
        person.money += value
        print(person.name, "取了%d钱" % value)


xm = Person("小明", 0)
zsyh = Bank("招商", 100000)
zsyh.draw_money(xm, 10000)
```



