# Python 简介
**Python介绍**

**【我也不喜欢看大段的文字，既然要学这门语言，那必要的文字介绍还是要看的哈】**

小时不识月，呼作白玉盘。很多人习惯地（甚至还会配合着鄙夷的眼神和标签）说Python不过是一种脚本语言而已，实际上这种说法是非常不准确的，完全不能体现出Python的强大。严格来说，**Python是一门跨平台、开源、免费的解释型高级动态编程语言**。除了解释执行，Python还支持伪编译将源代码转换为字节码来优化程序提高运行速度和对源代码进行保密，并且支持使用py2exe、pyinstaller、cx\\_Freeze或其他类似工具将Python程序及其所有依赖库打包为扩展名为exe的可执行程序，从而可以脱离Python解释器环境和相关依赖库而在Windows平台上独立运行；Python支持命令式编程、函数式编程，完全支持面向对象程序设计，语法简洁清晰，并且拥有大量的几乎支持所有领域应用开发的成熟扩展库；也有人喜欢把Python称为“胶水语言”，因为它可以把多钟不同语言编写的程序融合到一起实现无缝连接，更好地发挥不同语言和工具的优势，满足不同领域的需求。

Python是一种**解释型、面向对象**的语言。

由吉多·范罗苏姆（Guido van Rossum）于1989年发明，1991年正式公布。官网： www.python.org

Python单词是“大蟒蛇”的意思。但是龟叔不是喜欢蟒蛇才起这个名字，而是正在追剧：英国电视喜剧片《蒙提·派森的飞行马戏团》\(Monty Python and the Flying Circus\)。

**特点**

**1.可读性强**

可读性远比听上去重要的多得多。一个程序会被反复的修改，可读性强意味着让你可以在更短时间内学习和记忆，直接提高生产率。

**2.简洁，简洁，简洁**

研究证明，程序员每天可编写的有效代码数是有限的。完成同样功能只用一半的代码，其实就是提高了一倍的生产率。Python是由 C语言开发，但是不再有 C语言中指针等复杂数据类型，Python的简洁性让开发难度和代码幅度大幅降低，开发任务大大简化。程序员再也不需要关注复杂的语法，而是关注任务本身。



1.面向对象

2.免费和开源

3.可移植性和跨平台

Python会被编译成与操作系统相关的二进制代码，然后再解释执行。这种方式和java类似，大大提高了执行速度，也实现了跨平台。

1.丰富的库（丰富的标准库，多种多样的扩展库）

2.可扩展性。可嵌入到 C和 C++语言。胶水式语言。



**应用范围
**

> 1.科学计算
>
>2.人工智能
>
>3.WEB服务端和大型网站后端。YouTube、gmail等应用基于 python开发。
>
>4.GUI开发（图形用户界面开发）
>
>5.游戏开发
>
>6.移动设备
>
>7.嵌入式设备
>
>8.系统运维
>
>9.大数据
>
>10.云计算

**什么时候不应该用 Python**

1. Python是解释执行。性能较低。因此，一些影响性能的功能可以使用 C/C++/JAVA/GO（GO是一种新语言，写起了像 Python，性能像 C）去开发。
不过，不用担心 Python解释器会越来越快。

**版本和兼容问题解决方案**

目前主要两个版本：Python2和 Python3
Python2：
2000年 10月发布。最新版本是 2.7，已经停止更新，不会再有 2.8以后了。预计2020年退出历史舞台。

Python3：
2008年发布。Python3有了较大的提升，不兼容 Python2。

**兼容问题解决：**

1. Python3的很多新特性也被移植到了 Python2.7，作为过渡。如果程序可以在 2.7运行，可以通过一个名为 2to3（Python自带的一个脚本）的转换工具无缝迁移到 Python3.

2.建议大家学习从 Python3开始，毕竟这才是未来。
