## 时间模块

![](http://www.python87.com/uploads/allimg/190821/1-1ZR1113134Z0.jpg)

## 时间模块

此模块提供了时间相关的函数，且一直可用。

## 时间简介

Python 提供了一个 `time` 和 `calendar` 模块可以用于格式化日期和时间。

- 公元纪年是从公元 0000年1月1日0时开始的

- 计算机中时间的表示是从“`1970年 1月 1日 00:00:00`”开始，以`毫秒`（1/1000秒）进行计算,之后每过一秒时间+1。

- 我们也把 1970年这个时刻成为“unix时间点”。这样，我们就把时间全部用数字来表示了。

- python中可以通过 `time.time()`获得当前时刻，返回的值是`以秒为单位`，带微秒（1/1000毫秒）精度的浮点值。例如：1530167364.8566。

- UTC 时间 (Coordinated Universal Time) 是从Greenwich时间开始计算的.
UTC 时间不会因时区问题而产生错误

- DST 阳光节约时间(Daylight Saving Time)，又称夏令时, 是一个经过日照时间修正后的时间

## 时间模块的使用

```
导入方式

import time
# 或
from time import xxx
# 或
from time import *
```

| 数据 | 描述 |
| :--: | :--: |
| time.altzone | 夏令时时间与UTC时间差(秒为单位) |
| time.daylight | 夏令时校正时间 |
| time.timezone | 本地区时间与UTC时间差(秒为单位) |
| time.tzname | 时区名字的元组，第一个名字为未经夏令时修正的时区名,第一个名字为经夏令时修正后的时区名 |

注： CST为中国标准时间(China Standard Time UTC+8:00)

## 时间相关函数

| 函数名 | 描述 |
| :--: | :--: |
| time.time() | 返回从计算机元年至当前时间的秒数的浮点数(UTC时间为准) |
| time.gmtime([secs]) | 用给定秒数转换为用UTC表达的时间元组(缺省返回当前时间元组) |
| time.localtime([secs]) | 将UTC秒数时间转换为日期元组（以本地时间为准) |
| time.mktime(tuple) | 将本地日期时间元组转换为新纪元秒数时间(UTC为准) |
| time.asctime([tuple]) | 将时间元组转换为日期时间字符串 |
| time.sleep(secs) | 让程序按给定秒数的浮点数睡眠一段时间 |


## 时间元祖

- 时间元组是一个9个整型元素组成的,这九个元素自前至后依次为:
  - 四位的年(如: 1993)
  - 月 (1-12)
  - 日 (1-31)
  - 时 (0-23)
  - 分 (0-59)
  - 秒 (0-59)
  - 星期几 (0-6, 周一是 0)
  - 元旦开始日 (1-366)
  - 夏令时修正时间 (-1, 0 or 1).
- 注：
  - 如果年份值小于100,则会自动转换为加上1900后的值
模块名: time

```
import time
# 获取时间元祖
gmt = time.gmtime()

print(gmt)
"""
time.struct_time(
    tm_year=2020,           年
    tm_mon=1,               月
    tm_mday=2,              日
    tm_hour=9,              时
    tm_min=20,              分
    tm_sec=17,              秒
    tm_wday=3,              星期(从0开始算起)
    tm_yday=2,              一个月的第几天
    tm_isdst=0              夏令时(几乎用不到)
)
"""
```

## 获取时间戳

时间戳是指格林威治时间1970年01月01日00时00分00秒(北京时间1970年01月01日08时00分00秒)起至现在的总秒数。


```
import time

timestamp = time.time()

print(timestamp)

执行结果：1577956749.8488483
```


**【操作】源代码：**

```
import time

# 获取当前时间为止的整型 秒
a = int(time.time())

# 获取 分钟
m = a / 60       # 这样获取的是浮点数，我们为了方便计算都取整数
m = a // 60      # 1分钟 = 60秒

# 获取 小时
h = m // 60      # 1小时 = 60分钟

# 获取 天
d = h // 24      # 1天 = 24小时

# 获取 年
y = d // 365     # 1年 = 365天  这里不考虑闰月什么的

print(y)         # 49
```

## 时间字符串 --> 时间元祖

`strptime(时间字符串，时间字符串的格式)`,前后两个参数格式相同，可以自定义
```
import time

year = int(input("请输入年份："))
month = int(input("请输入月份："))
day = int(input("请输入日期："))
hour = int(input("请输入小时："))

tuple_time = time.strptime("%d-%d-%d" % (year, month, day), "%Y-%m-%d")

print(tuple_time)
```
执行结果：
```
请输入年份：2020
请输入月份：1
请输入日期：1
请输入小时：12
time.struct_time(tm_year=2020, tm_mon=1, tm_mday=1, tm_hour=0, tm_min=0, tm_sec=0, tm_wday=2, tm_yday=1, tm_isdst=-1)

```

## 时间元祖 --> 时间戳

使用 `time.mktime()` 函数来转换

```
import time

year = int(input("请输入年份："))
month = int(input("请输入月份："))
day = int(input("请输入日期："))
hour = int(input("请输入小时："))

tuple_time = time.strptime("%d-%d-%d" % (year, month, day), "%Y-%m-%d")

timestamp = time.mktime(tuple_time)

print(timestamp)
```
执行结果：
```
请输入年份：2020
请输入月份：1
请输入日期：1
请输入小时：12
1577851200.0

```

----
### 获取某月日历

`Calendar模块`有很广泛的方法用来处理`年历`和`月历`，例如打印某月的月历：

```
import calendar

cal = calendar.month(2020, 1)

print("以下输出2020年1月份的日历:")
print(cal)
```

执行结果：

```
以下输出2020年1月份的日历:
    January 2020
Mo Tu We Th Fr Sa Su
       1  2  3  4  5
 6  7  8  9 10 11 12
13 14 15 16 17 18 19
20 21 22 23 24 25 26
27 28 29 30 31
```

```
参考文档：
1. https://www.runoob.com/python/python-date-time.html
```
