**\_\_init\__\.py 文件**

是包内必须存在的文件

会在包加载时被自动调用

**\_\_all\__**

记录from 包 import * 语句需要导入的模块

**案例：**



```
my_project /
main.py        
common/
    __init__.py
    double_list_helper.py
    list_helper.py
skill_system/
    __init__.py
    skill_deployer.py
    skill_manager.py
```

**练习题:**

1.在main.py中调用skill_deployer.py。

2.在skill_deployer.py中调用skill_manager.py。

3.在skill_manager.py中调用double_list_helper.py。

4.在list_helper.py中调用main.py。

要求：在所有的调用过程中，要包含函数、类、实例方法、静态方法。




