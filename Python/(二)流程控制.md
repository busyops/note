## 流程控制

### 1. if语句

- 单分支

```python
if 条件:
    代码块
 
示例：
age = 20
if age >= 18:
    print("你是成年人")
```

- 双分支

```python
if 条件:
    代码块1
else:
    代码块2
    
示例：
age = 16
if age >= 18:
    print("你是成年人")
else:
    print("你是未成年人")
```

- 多分支

```python
if 条件1:
    代码块1
elif 条件2:
    代码块2
else:
    代码块3
    
示例：
score = 75
if score >= 90:
    print("优秀")
elif score >= 60:
    print("及格")
else:
    print("不及格")
```

- 特殊写法

```python
<值1> if <条件> else <值2>

示例：
age = 20
x = "大" if age >= 18 else "小"
print(x) 

如果 <条件> 成立，结果就是 <值1>；否则结果是 <值2>。
```



### 2. for循环

```python
for 变量 in 可迭代对象:
    循环体
    
示例：
fruits = ["apple", "banana", "cherry"]
for fruit in fruits:
    print(fruit)
```

- 结合else字句：如果中途 `break` 了，`else` 不会执行。

```python
for i in range(3):
    print(i)
else:
    print("循环正常结束，没有被 break则执行")
```



## 3. while循环

```python
while 条件:
    循环体

示例：
i = 0
while i < 5:
    print(i)
    i += 1
```

- 结合else子句，如果中途 `break` 了，`else` 不会执行。

```python
i = 0
while i < 3:
    print(i)
    i += 1
else:
    print("循环正常结束则执行")
```



## 4. 循环控制语句

- `break` —— **终止整个循环**

```python
for i in range(10):
    if i == 5:
        break
    print(i)
```

输出：

```python
0
1
2
3
4
```

一旦 `i == 5`，整个循环结束。



- `continue` —— **跳过本次循环，继续下一轮**

```python
for i in range(5):
    if i == 2:
        continue
    print(i)
```

输出：

```python
0
1
3
4
```

`i == 2` 时跳过了，不执行 `print(i)`。



- `pass` —— **占位，不做任何操作**

```python
for i in range(3):
    if i == 1:
        pass  # 什么也不做
    print(i)
```

输出：

```python
0
1
2
```

`pass` 通常用于：**写代码框架**时，占个位，语法上必须有语句，但你暂时不想写任何操作