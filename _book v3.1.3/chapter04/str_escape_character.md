
# 转义字符

1.改变字符的原始含义。

| 字符 | 含义 |
| :--: | :--: |
| \' | 一个单引号 |
| \" | 一个双引号 |
| \n | 换行 |
| \t | 水平制表符 |
| \v | 垂直制表符 |
| \a | 响铃(BEL) |
| \b | 退格(BS)将当前位置移到前一列 |
| \r | 回车(CR)将当前位置移到本行开头 |
| \f | 换页(FF)将当前位置移动到下页开头 |
| `\\` | 一个反斜杠\ |
| \0 | 空字符 |
| \? | 一个问号 |
| \ddd | 1到3位八进制数所代表的任意字符 |
| \xhh | 十六进制数所代表的任意字符 |

转义字符\可以转义很多字符，比如\n表示换行，\t表示制表符，字符\本身也要转义，所以\\表示的字符就是\。

演示代码

```
print('I\'m ok.')

print('I\'m learning\nPython.')

print('\\\n\\')

print('\\\t\\')

print(r'\\\t\\')

print('''line1
line2
line3''')

```

运行结果：
![](http://www.python87.com/uploads/allimg/200103/1_2238319211.png)


2.原始字符串：取消转义。

```
a = r"C:\newfile\test.py"

print(a)

url = "C:\\nltk_data\\aodels\\bmt15_eval"
# 原始字符串(没有转义符)
url = r"C:\nltk_data\aodels\bmt15_eval"
print(url)
```
运行结果：

```
C:\newfile\test.py
```
