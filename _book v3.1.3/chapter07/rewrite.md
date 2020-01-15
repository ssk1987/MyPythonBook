# 重写

子类实现了父类中相同的方法（方法名、参数），在调用该方法时，实际调用的是子类的方法。

## 1.内置可重写函数


Python中，以双下划线开头、双下划线结尾的是系统定义的成员。我们可以在自定义类中进行重写，从而改变其行为。

```
__str__函数：将对象转换为字符串(对人友好的)

__repr__函数：将对象转换为字符串(解释器可识别的)
```



## 2.运算符重载

> 定义：让自定义的类生成的对象(实例)能够使用运算符进行操作。

演示代码：

```
class Vector1:
    def __init__(self, x):
        self.x = x

    def __str__(self):
        return "一维向量的分量是：" + str(self.x)

    def __add__(self, other):
        return Vector1(self.x + other)

    def __radd__(self, other):
        return Vector1(self.x + other)

    def __iadd__(self, other):
        self.x += other
        return self



v01 = Vector1(10)
print(v01 + 2)  # v01.__add__(2)

# 练习:实现自定义类的对象与数值的减法，乘法运算。
# 略...
print(2 + v01)
# 练习:实现数值与自定义类的对象的减法，乘法运算。
# 略...

print(id(v01))
# 重写__iadd__，实现在原对象基础上的变化。
# 如果重写__iadd__,默认使用__add__，一般会产生新对象.
v01 += 2
print(v01,id(v01))


# list01 = [1]
# print(id(list01))
# # 生成新对象
# re = list01 + [2]
# print(re,id(re))
# # 在原有对象基础上，累加.
# list01 += [2]
# print(list01,id(list01))
```

## 3.算数运算符

| 方法名 | 运算符和表达式 | 说明 |
| -- | -- | -- |
| \_\_add__(self,rhs) | self + rhs | 加法 |
| \_\_sub__(self,rhs) | self - rhs | 减法 |
| \_\_mul__(self,rhs) | self * rhs | 乘法 |
| \_\_truediv__(self,rhs) | self / rhs | 除法 |
| \_\_floordiv__(self,rhs) | self // rhs | 地板除 |
| \_\_mod__(self,rhs) | self % rhs | 取模(求余) |
| \_\_pow__(self,rhs) | self ** rhs | 幂 |

## 4.反向算数运算符重载

| 方法名 | 运算符和表达式 | 说明 |
| -- | -- | -- |
| \_\_radd__(self,lhs) | lhs + self | 加法 |
| \_\_rsub__(self,lhs) | lhs - self | 减法 |
| \_\_rmul__(self,lhs) | lhs * self | 乘法 |
| \_\_rtruediv__(self,lhs) | lhs / self | 除法 |
| \_\_rfloordiv__(self,lhs) | lhs // self | 地板除 |
| \_\_rmod__(self,lhs) | lhs % self | 取模(求余) |
| \_\_rpow__(self,lhs) | lhs ** self | 幂 |

## 5.复合运算符重载

| 方法名 | 运算符和表达式 | 说明 |
| -- | -- | -- |
| \_\_iadd__(self,rhs) | self += rhs | 加法 |
| \_\_isub__(self,rhs) | self -= rhs | 减法 |
| \_\_imul__(self,rhs) | self *= rhs | 乘法 |
| \_\_itruediv__(self,rhs) | self /= rhs | 除法 |
| \_\_ifloordiv__(self,rhs) | self //= rhs | 地板除 |
| \_\_imod__(self,rhs) | self %= rhs | 取模(求余) |
| \_\_ipow__(self,rhs) | self **= rhs | 幂 |

## 6.比较运算重载
| 方法名 | 运算符和表达式 | 说明 |
| -- | -- | -- |
| \_\_lt__(self,rhs) | self < rhs | 小于 |
| \_\_le__(self,rhs) | self <= rhs | 小于等于 |
| \_\_gt__(self,rhs) | self > rhs | 大于 |
| \_\_ge__(self,rhs) | self >= rhs | 大于等于 |
| \_\_eq__(self,rhs) | self == rhs | 等于 |
| \_\_ne__(self,rhs) | self != rhs | 不等于 |


## 7.演示代码

```
# 内置可重写函数
class StudentModel:
    def __init__(self, name="", age=0, score=0, id=0):
        self.name = name
        self.age = age
        self.score = score
        self.id = id

    # 对象 --> 字符串 (随意格式)
    def __str__(self):
        return "我叫%s,编号是%d,年龄是%d,成绩是:%d"%(self.name,self.id,self.age,self.score)

    # 对象 --> 字符串(解释器可识别,有格式)
    def __repr__(self):
        return "StudentModel('%s',%d,%d,%d)"%(self.name,self.age,self.score,self.id)


s01 = StudentModel("无忌",27,100,101)
str01 = str(s01)
print(str01)
print(s01)

str02 =repr(s01)
print(str02)

# 根据字符串执行python代码
re = eval("1+2*5")
# exec
print(re)

# 克隆对象
# repr 返回python格式的字符串
# eval根据字符串执行代码
s02 = eval(repr(s01))
s02.name = "老张"
print(s01.name)
```























