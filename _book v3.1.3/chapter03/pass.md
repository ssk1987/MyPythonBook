## pass 语句

Python pass 是空语句，是为了保持程序结构的完整性。  

pass 不做任何事情，一般用做占位语句。  

Python 语言 pass 语句语法格式如下：

```
pass
```

**实例测试：**

```
#!/usr/bin/python
# -*- coding: UTF-8 -*- 
 
# 输出 Python 的每个字母
for letter in 'Python':
   if letter == 'h':
      pass
      print '这是 pass 块'
   print '当前字母 :', letter
 
print "Good bye!"

# 以上实例执行结果：
"""
当前字母 : P
当前字母 : y
当前字母 : t
这是 pass 块
当前字母 : h
当前字母 : o
当前字母 : n
Good bye!
"""
```

**笔记：**
pass 一般用于占位置。 
 
在 Python 中有时候会看到一个 def 函数:

```
def sample(n_samples):
    pass
```

该处的 pass 便是占据一个位置，因为如果定义一个空函数程序会报错，当你没有想好函数的内容是可以用 pass 填充，使程序可以正常运行。


```
本文内容来源于：https://www.runoob.com/python/python-pass-statement.html    2019-11-06 22:53
```

