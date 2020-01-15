# [容器/序列] 网络相关

- 将两个列表删除重复项并合并

如何将两个列表合并并扣除其中的重复项呢?可以看看这个方法，看起来是不是挺“卑鄙”的。挖python墙角感觉，但更好的方法还确实没想出来。实际分析中去重可能不多，但统计众数比较多，如果是string、列表，如何统计重复内容数量，思路类似。

```
def union(a,b):
    return list(set(a + b))

union([1, 2, 3, 4, 5], [6, 2, 8, 1, 4])

# 答案：[1,2,3,4,5,6,8]
```

- 将列表去重

```
def unique_elements(numbers):
    return list(set(numbers))

unique_elements([1, 2, 3, 2, 4])

# 答案：[1, 2, 3, 4]
```

- 找到一组数字的均值

虽然有mean函数，但比如你想自己算依稀的东西用到mean的时候，你可以自己造个，也就两行而已。

```
def average(*args):
    return sum(args, 0.0) / len(args)
average(5, 8, 2)

# 5.0
```

- 检查一个数组是不是都是唯一的数值

```
def unique(list):
    if len(list)==len(set(list)):
        print("所有数据都是唯一的")
    else:
        print("并不唯一")

unique([1,2,3,4,5])
# 所有数据都是唯一的
```

- 找到列表频率最大的数据

```
def most_frequent(list):
    return max(set(list), key = list.count)

numbers = [1, 2, 3, 2, 4, 3, 1, 3]
most_frequent(numbers)

# 3
```

- 角度变弧度

π在math 库中是有定义的,就叫做math.pi

```
import math

def degrees_to_radians(deg):
    return (deg * math.pi) / 180.0

degrees_to_radians(90)
# 1.5707963267948966
```

- 打印运行计算花费时间

这个时间跟电脑速度有关

```
import time
start_time = time.time()
a,b = 5,10  #随便一个过程
c = a+b     #随便一个过程
end_time = time.time()
time_taken = (end_time- start_time)*(10**6)
print("运行这个耗费微秒数为:", time_taken)

# 运行这个耗费微秒数为: 2.1457672119140625
```

- 找到一组数的最大公因数

借助工具functools

```
from functools import reduce
import math

def gcd(numbers):
    return reduce(math.gcd, numbers)

gcd([24,108,90])

# 6
```

- 列表连续操作

```
numbers = [1, 2, 3]

def squares(nums):
    return [number**2 for number in nums]

 squares(numbers)

# [1, 4, 9]
```

- 切片操作

切片用于从给定序列中提取元素的连续序列或子序列。以下函数用于合并两个切片操作的结果。首先，我们将列表从索引d切到末尾，然后从开始切成索引d。

```
def rotate(arr, d):
    return arr[d:] + arr[:d]

if __name__ == '__main__':
    arr = [1, 2, 3, 4, 5]
    arr = rotate(arr, 2)
    print (arr)

# 结果：[3, 4, 5, 1, 2]
```

- 使用链功能

最后的代码段用于从一行开始调用多个函数并评估结果。

```
def add(a, b):
    return a + b
def subtract(a, b):
    return a - b
a, b = 5, 10
print((subtract if a > b else add)(a, b))  # 15
print((subtract if a < b else add)(a, b))  # -5
```
