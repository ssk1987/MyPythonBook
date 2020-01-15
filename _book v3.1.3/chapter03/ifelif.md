## if 语句的真值表达式


```
if 100:
    print("真值")

# 等同于

if bool(100):
    print("真值")
```

### 相关练习

```
if 'a' < 'b':
    print("Love")
# 输出 Love

while 'a' < 'b':
    print("Love")
# 死循环
```
