## global 语句 / 关键字

1.作用：

在函数内部修改全局变量。

在函数内部定义全局变量(全局声明)。

2.语法：

```
global 变量1, 变量2, …
```

3.说明

在函数内直接为全局变量赋值，视为创建新的局部变量。

不能先声明局部的变量，再用global声明为全局变量

4.相关代码

```
参考 nonlocal语句.md 内的代码
```