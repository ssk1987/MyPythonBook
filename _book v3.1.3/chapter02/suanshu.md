## 基本算术运算符
| 运算符 | 说明 | 示例 | 结果 |
| :--: | :--: | :--: | :--: |
| + | 加法 | 2 + 2 | 4 |
| - | 减法 | 30 - 5 | 25 |
| * | 乘法 | 2 * 4 | 8 |
| / | 除法：结果为浮点数 | 8 / 2 | 4.0 |
| // | 地板除：除的结果去掉小数部分 | 7 // 2 | 3 |
| % | 求余 | 7 // 2 | 1 |
| ** | 幂运算 | 2 ** 3 | 8 |


**优先级从高到低： **
```
        ()
        **
        *  / % //
        +  -
```

**▲：除数为0.会产生异常：**

```
>>> 3 / 0

Traceback (most recent call last):
  File "<pyshell#8>", line 1, in <module>
    3 / 0
ZeroDivisionError: division by zero

零分割错误：被零分割
```

**▲：使用 divmod() 函数同时得到商和余数：**
```
>>> divmod(13, 3)

(4, 1)
```
> divmod()是一个函数，它返回的是一个元组；

下面的代码是以我目前会的知识做出来和divmod()函数功能差不多的函数，可以得出相同的结果
```
def cdmod1(a, b):
    c = a // b      # 取商
    d = a % b       # 取余数
    return (c, d)   # 返回一个元组

print(cdmod1(13, 3))# (4, 1)
```



