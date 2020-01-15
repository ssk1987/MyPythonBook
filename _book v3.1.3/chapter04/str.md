# 字符串str

是用来记录文本信息(文字信息)。

字面值：双引号

# 网络相关

- 分割一个字符串为一个列表

这个案例使用换行符分割的,实际应用中,随机应变。

```
def split_lines(s):
    return s.split('\n')

split_lines('50\n python\n snippets')

# ['50', ' python', ' snippets']
```

- 翻转字符串

这个案例告诉我们字符串的翻转用法,相应的简单字符串可以翻转,以后的图片\音频\视频,一样可以翻转.如果你在一个函数里用这个功能，可以解决某些场景里的问题。

```
language = "sumer-minus"   # SUMER是我公众号，minus是我一个网名

reversed_language = language[::-1]

print(reversed_language)  # sunim-remus
```

- 打印字符串x遍的小函数

从这里提取两个概念:1如何打印n遍,理解函数调用

```
def repeat(string, n):
    return (string * n)

a=repeat('oop!',10)
print(a)

>>>oop!oop!oop!oop!oop!oop!oop!oop!oop!oop!
```

- 检查一个字符串是否与他的翻转相同

这个小代码把字符串翻转,和bool又一次加深理解

```
def palindrome(string):
    return string == string[::-1]

print(palindrome('python')) # False
```

- 把一个列表拼装成字符串

用到了列表join方法，数据分析中可能用的多的是pandas的DataFrame格式的矩阵、张量，但一维这些东西一样会遇到使用。

```
strings = ['老虎', '老鼠', '蟑螂']
print('kill'.join(strings))

# 老虎kill老鼠kill蟑螂
```








