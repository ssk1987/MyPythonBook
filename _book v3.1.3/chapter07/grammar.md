# 继承语法

## 1.代码

```
class 子类(父类):
 	def __init__(self,参数列表):
		super().__init__(参数列表)
		self.自身实例变量 = 参数
```

## 2.说明

-- 子类拥有父类的所有成员。

-- 子类如果没有构造函数，将自动执行父类的，但如果有构造函数将覆盖父类的。

此时必须通过super()函数调用父类的构造函数，以确保父类属性被正常创建。

## 3.继承-方法

```
"""
    继承 -- 方法
        财产：钱不用孩子挣，但是可以花。
        皇位：江山不用孩子打，但是可以坐。
        代码：子类不用写，但是可以用。
"""

# 多个子类在概念上一致的，所以就抽象出一个父类.
# 多个子类的共性，可以提取到父类中.
# 在实际开发过程中：
# 从设计角度讲：先有子，再有父.
# 从编码角度讲：先有父,再有子.

class Person:
    def say(self):
        print("说话")

class Student(Person):
    def study(self):
        print("学习")

class Teacher(Person):
    def teach(self):
        print("讲课")

s01 = Student()
# 子类对象可以调用子类成员，也可以调用父类成员.
s01.study()
s01.say()  # 父类成员

p01 = Person()
# 父类对象只可以调用父类成员,不能调用子类成员.
p01.say()

t01 = Teacher()

# python 内置函数
# 1. 判断对象是否属于一个类型
# "老师对象" 是 一个老师类型
print(isinstance(t01, Teacher))  # True
# "老师对象" 不是 一个学生类型
print(isinstance(t01, Student))  # Flase
# "老师对象" 是 一个人类型
print(isinstance(t01, Person))  # True

# 2.判断一个类型是否属于另一个类型
# "老师类型" 不是 一个学生类型
print(issubclass(Teacher, Student))  # Flase
# "老师类型" 不是 一个学生类型
print(issubclass(Teacher, Person))  # True
# "人类型" 不是 一个老师类型
print(issubclass(Person, Teacher))  # Flase
```

## 4.继承-变量

**内存图**

![](http://www.python87.com/uploads/allimg/200104/1_2339243862.jpg)

```
class Person:
    def __init__(self, name):
        self.name = name

"""
class Student(Person):
    # 子类若没有构造函数，使用父类的.
    pass

s01 = Student()
print(s01.name)
"""

class Student(Person):
    # 子类若具有构造函数，则必须先调用父类构造函数。
    def __init__(self, name, score):
        super().__init__(name)
        self.score = score

p01 = Person("李四")
print(p01.name)

s01 = Student("张三", 100)
print(s01.score)
print(s01.name)
```

## 5.继承-设计(1)

**内存图**

![](http://www.python87.com/uploads/allimg/200104/1_2339247153.jpg)

```
# 需求：老张开车去东北
# 变化：    坐飞机
#          坐火车
#          骑车
#          ...

# 违反了开闭原则：
#  如果增加火车，需要增加"火车类",再修改人类中的go_to方法.

class Person:
    def __init__(self, name):
        self.name = name

    def go_to(self, vehicle, str_position):

        # 如果是汽车
        if type(vehicle) == Car:
            vehicle.run(str_position)
        # 否则如果是飞机
        elif type(vehicle) == Airplane:
            vehicle.flay(str_position)


class Car:
    def run(self, str_position):
        print("汽车开到", str_position)


class Airplane:
    def flay(self, str_position):
        print("飞机飞到", str_position)


p01 = Person("老张")
c01 = Car()
a01 = Airplane()
p01.go_to(c01, "东北")
p01.go_to(a01, "东北")

```

## 5.继承-设计(2)

**内存图**

![](http://www.python87.com/uploads/allimg/200104/1_2339243274.jpg)

```
# 需求：老张开车去东北
# 变化：    坐飞机
#          坐火车
#          骑车
#          ...

class Vehicle:
    """
        交通工具,代表所有具体的交通工具(火车/飞机..)
        继承：隔离子类变化,将子类的共性(坐/飞..)提取到父类(运输)中.
    """

    def transport(self, str_position):
        # 因为父类太过于抽象，所以写不出方法体.
        pass


# 客户端代码，用交通工具。
class Person:
    def __init__(self, name):
        self.name = name

    def go_to(self, vehicle, str_position):
        # 多态：调用父，执行子.
        # 调用的是交通工具的运输方法
        # 执行的是飞机的运输方法或者汽车的运输方法
        vehicle.transport(str_position)


# -------以上是架构师完成的--以下是程序员完成的-----
class Car(Vehicle):
    def transport(self, str_position):
        print("汽车开到", str_position)


class Airplane(Vehicle):
    def transport(self, str_position):
        print("飞机飞到", str_position)


p01 = Person("老张")
c01 = Car()
a01 = Airplane()
p01.go_to(c01, "东北")
p01.go_to(a01, "东北")
```






