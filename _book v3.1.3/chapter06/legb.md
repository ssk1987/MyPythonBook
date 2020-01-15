# 作用域LEGB

1.作用域：变量起作用的范围。

2.Local局部作用域：函数内部。

3.Enclosing  外部嵌套作用域 ：函数嵌套。

4.Global全局作用域：模块(.py文件)内部。

5.Builtin内置模块作用域：builtins.py文件。

图示：

![legb](http://www.python87.com/uploads/allimg/191231/1_2040577511.png "图示")


### 变量名的查找规则

1. 由内到外：L -> E -> G -> B

2. 如果某个name映射在局部（local）命名空间中没有找到，接下来就会在闭包作用域（enclosed）进行搜索，如果闭包作用域也没有找到，Python就会到全局（global）命名空间中进行查找，最后会在内建（built in）命名空间搜索，如果一个名称在所有命名空间中都没有找到，就会产生一个NameError的错误。

### 局部变量

1.定义在函数内部的变量(形参也是局部变量)

2.只能在函数内部使用

3.调用函数时才被创建，函数结束后自动销毁

### 全局变量

1.定义在函数外部,模块内部的变量。

2.在整个模块(py文件)范围内访问（但函数内不能将其直接赋值）。

---

**【操作】测试**

```
str = 'global'

def outer():
    str = 'outer'

    def inner():
        str = 'inner'
        print(str)

    inner()

outer()

```
**动画演示图：**

![](http://www.python87.com/uploads/allimg/190917/1-1Z91G54119556.gif)

---

**【注意】**

> 上面演示的代码中 str 这个变量，其实是Python内部的 str()函数；

> 如果将代码中的str变量全部注释掉，依然不会报错。

> 但是如果将 str变量名称变换掉就会报错---> NameError 的错误。
