# 内置函数

`isinstance(obj, class_or_tuple)`

返回这个对象obj 是否是某个类的对象,或者某些类中的一个类的对象。

## 内存图

![](http://www.python87.com/uploads/allimg/200104/1_2339244251.jpg)

**演示代码：**

```
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
