# 可变／不可变类型在传参时的区别


## 1.不可变类型参数有:

数值型(整数，浮点数,复数)

布尔值bool

None 空值

字符串str

元组tuple

固定集合frozenset

## 2.可变类型参数有:

列表 list

字典 dict

集合 set

## 3.传参说明：

不可变类型的数据传参时，函数内部不会改变原数据的值。

可变类型的数据传参时，函数内部可以改变原数据。

## 4.相关演示代码(※记得调试※)

```
# 如何解释下列程序运行的结果
def extendlist(val, list_target=[]):
    for i in range(val):
        list_target.append(i)
    print(list_target)

extendlist(3)          # [0, 1, 2]
extendlist(3)          # [0, 1, 2, 0, 1, 2]

list02 = []
extendlist(3, list02)  # [0, 1, 2]

# 解释
# 解释器会将函数定义到方法区（存储一份），连同默认参数一起创建。
# 所以不指定参数时，使用的就是那一份列表对象。
# 总结：默认参数，不要使用可变参数。
```

## 5.类似的面试题

```
def extendlist(val, list=[]):
    list.append(val)
    return list

list1 = extendlist(10)
list2 = extendlist(123, [])
list3 = extendlist('a')

print("list1 = %s" % list1) # list1 = [10, 'a']
print("list2 = %s" % list2) # list2 = [123]
print("list3 = %s" % list3) # list3 = [10, 'a']

# 上面这段代码的输出结果是什么(2分)？请解释原因(5分)？
```


































