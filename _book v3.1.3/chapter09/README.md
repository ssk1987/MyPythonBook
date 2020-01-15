## 案例：项目内各个包内的模块怎么互相调用???

案例1：

![](http://www.python87.com/uploads/allimg/191127/1-19112G30145916.png)


```
"""
案例：
my_ project /
main.py
common/
    __init__.py
   double_list_helper.py
   list_helper.py
skill_system/
    __init__.py
    skill_deployer.py
    skill_manager.py
练习:
1.在main.py中调用skill_deployer.py。
2.在skill_deployer.py中调用skill_manager.py。
3.在skill_manager.py中调用double_list_helper.py。
4.在list_helper.py中调用main.py。
要求：在所有的调用过程中，要包含函数、类、实例方法、静态方法。
"""
```
![](http://www.python87.com/uploads/allimg/191127/1-19112G30410U4.png)

### 参考代码
```
# main.py 文件内代码
from skill_system.skill_deployer import *


class MainTest(object):
    @staticmethod
    def print_main():
        print("print-----MainTest")


# 1.在main.py中调用skill_deployer.py。

s1 = Student("张三", 25)
s1.fly()  # 张三 25

# *******************************************************************************
# double_list_helper.py 文件内代码
class A(object):
    def add_a(self):
        print("A --- add_a()")

# *******************************************************************************
# list_helper.py 文件内代码
from main import *

class B:
    @staticmethod
    def print_B():
        print("B---print-b")

# 4.在list_helper.py中调用main.py。
# a01 = MainTest()
MainTest.print_main()

# *******************************************************************************
# skill_deployer.py 文件内代码
from skill_system.skill_manager import *

class Student(object):
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def fly(self):
        print(self.name, self.age)


# 2.在skill_deployer.py中调用skill_manager.py。
re = print_d(5)
print(re)  # 3125

# *******************************************************************************
# skill_manager.py 文件内代码
from common.double_list_helper import *
def print_d(a):
    return a ** a

# 3.在skill_manager.py中调用double_list_helper.py。

s1 = A()
s1.add_a()  # A --- add_a()
```
