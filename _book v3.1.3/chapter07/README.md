# 面向对象复习

## 类和对象

```
类和对象
    类:抽象　　　向量 class Vector2    str  int   list
    对象:具体　　1,2   Vector2(1,2)   "a"   1    [1,2]
    之间的区别：类与类行为不同
               对象与对象数据不同
        　     　Vector2(1,2)　Vector2(3,4)
               同一个类型的多个对象,数据不同(1,2/3,4),行为(求方向，求大小)相同.

        类成员：
            实例：对象的数据(变量)，对象的行为(方法).
            类:类的数据(变量),类的行为(方法).
                可以被所有对象共同操作的数据

            静态方法:
                实例方法操作实例变量，表示"个体"行为.
                类方法操作类变量，表示"大家"行为.
                静态方法不能操作数据，表示为函数都可以.
```

## 封装

```
"""
    封装
        数据角度：将多个变量封装到一个自定义类中。
                优势：
                    符合人类的思考方式
                    可以将数据与对数据的操作封装到一起

        功能角度：对外提供必要的功能,隐藏实现的细节.
                 DoubleListHelper.get_elements()
                 -- 私有化：将名称命名为以双下划线开头.
                          内部修改成员名称
                 -- 属性：对实例变量的保护(拦截读/写操作)
                 -- __slots__:限定类创建的对象只能有固定的实例变量.

        设计角度：
            分而治之:将大的需求分解为多个类，每个类负责一个职责。
            变则疏之：遇到变化点单独封装为一个类
            ------------------
            高内聚：一个类有且只有一个发生变化的原因
            低耦合：类与类的关系松散
"""
```

```
"""
    复习
        面向对象：考虑问题从对象的角度出发.
        抽象：从多个事物中，舍弃个别的/非本质的特征(不重要)，
             抽出共性的本质(重要的)过程。
        三大特征：
            封装：将每个变化点单独分解到不同的类中。
                例如：老张开车去东北
                做法：定义人类，定义车类。

            继承：重用现有类的功能和概念，并在此基础上进行扩展。
                   统一概念
                例如：图形管理器，统计圆形/矩形.....面积。
                做法：用图形类代表/约束，圆形/矩形..具有计算面积的方法.

            多态：调用父"抽象的"方法，执行子类"具体的"方法.
                重写：覆盖父类那个比较抽象的方法。
                例如：图形管理器调用图形的计算面积方法
                     具体图形必须重写图形的计算面积方法。
                继承是共性(计算面积)，多态个性(长*宽 / pi *r**2)。

        设计原则
            开闭原则：允许增加新功能，不允许修改客户端代码.
            单一职责：一个有且只有一个改变的原因.
            依赖倒置：调用抽象(父)，不要调用具体(子);
                    抽象不要依赖具体.
            组合复用：如果仅仅是代码的复用，优先使用组合.

        类与类关系
            泛化[继承](做成爸爸)
            关联(做成成员变量)
            依赖(做成方法参数)
"""
```

## 相关演示练习

```
"""
请用面向对象思想，描述以下场景：
    张无忌　教　赵敏　九阳神功
    赵敏　教　张无忌　化妆
    张无忌　上班　挣了　10000
    赵敏　上班　挣了　6000
    体会：对象区分数据的不同
"""
class Person:
    def __init__(self, name):
        self.name = name

    @property
    def name(self):
        return self.__name

    @name.setter
    def name(self, value):
        self.__name = value

    def teach(self, other, skill):
        print(self.name, "教", other.name, skill)

    def work(self, money):
        print(self.name, "上班挣了%d钱" % money)


zwj = Person("张无忌")
zm = Person("赵敏")
zwj.teach(zm, "九阳神功")
zm.teach(zwj, "化妆")
zwj.work(10000)
zm.work(6000)

```


```
"""
请用面向对象思想，描述以下场景：
    玩家(攻击力)攻击敌人(血量)，敌人受伤(掉血)，还可能死亡(掉装备，加分)。
    敌人(攻击力)攻击玩家，玩家(血量)受伤(掉血/碎屏),还可能死亡(游戏结束)。
    体会：类区别行为的不同
"""

class Player:
    def __init__(self, hp, atk):
        self.hp = hp
        self.atk = atk

    def attack(self, other):
        # 打的逻辑
        print("玩家攻击敌人")
        # 通过敌人对象地址，调用实例方法.
        other.damage(self.atk)

    def damage(self, value):
        print("玩家受伤")
        self.hp -= value
        if self.hp <= 0:
            self.__death()

    def __death(self):
        print("玩家死喽")
        print("游戏结束")


class Enemy:
    def __init__(self, hp, atk):
        self.hp = hp
        self.atk = atk

    def damage(self, value):
        # 受伤的逻辑
        print("敌人受伤了")
        self.hp -= value
        if self.hp <= 0:
            self.__death()

    # 私有的死亡方法
    def __death(self):
        # 死亡的逻辑
        print("死亡")
        print("掉装备")
        print("加分")

    def attack(self, other):
        print("敌人攻击玩家")
        other.damage(self.atk)


p01 = Player(1000, 100)
e01 = Enemy(200, 10)
p01.attack(e01)
e01.attack(p01)

p01.attack(e01)
```
