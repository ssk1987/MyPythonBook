# 相关练习题

**Exercise-1**

```
"""
    定义父类
        动物（行为：叫）

    定义子类
        狗（行为：跑）
        鸟（行为：飞）

    创建三个类型的对象
    体会：isinstance(对象,类型)
    体会：issubclass(类型,类型)
"""


class Animal:
    def shout(self):
        print("喊叫")


class Bird(Animal):
    def fly(self):
        print("飞")


class Dog(Animal):
    def run(self):
        print("跑")


animal = Animal()
bird = Bird()
dog = Dog()
print(isinstance(animal, Bird))
print(isinstance(dog, Animal))

print(issubclass(Animal, Bird))
print(issubclass(Dog, Animal))

```

**Exercise-2**

```
"""
    定义父类
        车（数据：品牌,速度）

    定义子类
        电动车（数据：电池容量,充电功率）

    创建两个对象
    画出内存图.
"""
class Car:
    """
        车
    """
    def __init__(self,brand,speed):
        self.brand = brand
        self.speed = speed

class Electrocar(Car):
    """
        电动车
    """
    def __init__(self,brand,speed,battery_capacity,charging_power):
        super().__init__(brand,speed)
        self.battery_capacity = battery_capacity
        self.charging_power = charging_power


c01 = Car("奔驰",230)
print(c01.brand)

e01 = Electrocar("比亚迪",120,15000,220)
print(e01.brand)
print(e01.charging_power)
```

**Exercise-3**

![](http://www.python87.com/uploads/allimg/200104/1_2339249535.jpg)

```
"""
    手雷炸了，可能伤害敌人/玩家的生命.
             还可能伤害未知事物(鸭子.房子....)
    要求：增加了新事物，不影响手雷。
    体会：继承的作用
         多态的体现
         设计原则
            开闭原则
            单一职责
            依赖倒置
    画出设计图
"""


class Granade:
    def __init__(self, atk):
        self.atk = atk

    def explode(self, damage_target):
        # 如果传入的不是子类，则报错.
        if not isinstance(damage_target, Damageable):
            raise ValueError("不是Damageable的子类")

        print("爆炸")
        # 多态:
        # 调用父类代表(玩家/敌人.....)的可以受伤者.
        # 执类行子(具体玩家/敌人.....)
        damage_target.damage(self.atk)


class Damageable:
    """
        可以受伤
        继承:统一多个子类的概念，隔离变化。
    """

    def damage(self, value):
        # 如果子类不重写，则异常。
        raise NotImplementedError()


# ------------------------------
class Player(Damageable):
    def __init__(self, hp):
        self.hp = hp

    def damage(self, value):
        self.hp -= value
        print("玩家受伤啦")
        print("碎屏")


class Enemy(Damageable):
    def __init__(self, hp):
        self.hp = hp

    def damage2(self, value):
        self.hp -= value
        print("敌人受伤喽")
        print("头顶爆字")


g01 = Granade(100)
e01 = Enemy(200)
p01 = Player(300)
g01.explode(p01)
```


**Exercise-4**

![](http://www.python87.com/uploads/allimg/200104/1_2348294901.jpg)

```
"""
    定义图形管理器类
        1. 管理所有图形
        2. 提供计算所有图形总面积的方法

    具体图形:
        圆形(pi × r ** 2)
        矩形(长*宽)
        ...

    测试：
        创建1个圆形对象，1个矩形对象，添加到图形管理器中.
        调用图形管理器的计算面积方法，输出结果。

    要求：增加新图形，不修改图形管理器的代码.
    体会：面向对象三大特征：
            封装/继承/多态
         面向对象设计原则：
            开闭/单一/倒置

"""


class GraphicManager:
    def __init__(self):
        self.__graphics = []

    def add_graphic(self, graphic):
        if isinstance(graphic, Graphic):
            self.__graphics.append(graphic)
        else:
            raise ValueError()

    def get_total_area(self):
        total_area = 0
        # 遍历图形列表，累加每个图形的面积
        for item in self.__graphics:
            # 多态：
            # 调用的是图形
            # 执行的是圆形/矩形...
            total_area += item.calculate_area()
        return total_area

class Graphic:
    def calculate_area(self):
        # 如果子类不重写，则异常.
        raise NotImplementedError()
#-----------------------------------
class Circle(Graphic):
    def __init__(self,radius):
        self.radius = radius

    def calculate_area(self):
        return 3.14 * self.radius **2


class Rectanlge(Graphic):
    def __init__(self,length,width):
        self.lenght = length
        self.width = width


    def calculate_area(self):
        return self.lenght *  self.width


c01 = Circle(5)
r01 = Rectanlge(10,20)
manager = GraphicManager()
manager.add_graphic(c01)
manager.add_graphic(r01)
re = manager.get_total_area()
print(re)
```



**Exercise-5**

内存图

![](http://www.python87.com/uploads/allimg/200104/1_2354336971.jpg)

```
"""
    定义员工管理器
        1.管理所有员工
        2. 计算所有员工工资

    员工：
        程序员：底薪 + 项目分红
        销售：底薪 + 销售额 * 0.05
        软件测试...
        ...

    要求：增加新岗位，员工管理器不变.
"""
class EmployeeManager:
    def __init__(self):
        self.__employees = []

    def add_employee(self, emp):
        self.__employees.append(emp)

    def get_total_saraly(self):
        total_saraly = 0
        for item in self.__employees:
            # 调用是抽象的员工类
            # 执行是具体的员工(程序员/销售..)
            total_saraly += item.calculate_salary()
        return total_saraly

class Employee:
    def __init__(self, base_salary):
        self.base_salary = base_salary

    def calculate_salary(self):
        return self.base_salary

# ---------------------------------------
class Programmer(Employee):
    def __init__(self, base_salary, bonus):
        super().__init__(base_salary)
        self.bonus = bonus

    def calculate_salary(self):
        # return self.base_salary + self.bonus
        # 扩展重写
        return super().calculate_salary()+ self.bonus

class Salesmen(Employee):
    def __init__(self, base_salary, sale_value):
        super().__init__(base_salary)
        self.sale_value = sale_value

    def calculate_salary(self):
        return self.base_salary + self.sale_value * 0.05

# 测试
manager = EmployeeManager()
manager.add_employee(Programmer(200000,500))
manager.add_employee(Salesmen(2000,1000))
print(manager.get_total_saraly())
```















