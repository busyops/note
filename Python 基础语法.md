# Python 基础语法



## 一、基础语法

### 1. 注释

```python
# 这是一个单行注释
print("Hello, world")  # 这是在代码后面的注释
```



### 2. 数据类型

- **整数**（int）：`1`, `-10`, `0`
- **浮点数**（float）：`3.14`, `-0.01`, `1.2e3`
- **布尔值**（bool）：`True`, `False`
- **字符串**（str）：`'abc'`, `"xyz"`, `'''多行'''`
- **复数**（complex）：`1 + 2j`

### 3. 数字进制表示

- 二进制：`0b1010`
- 八进制：`0o12`
- 十六进制：`0xA`

### 4. 转义字符

```
\n（换行）、\t（制表符）、\\（反斜杠）、\'（单引号）、\"（双引号）
```

### 5. 标识符命名规则

- 由字母、数字、下划线组成
- 不能以数字开头
- 不能使用 Python 保留关键字（如 `def`, `class`）
- 区分大小写，不允许使用中文

### 6. 变量与常量

```
age = 25     # 变量
PI = 3.1415  # 约定用大写表示常量
```



## 二、运算符

### 1. 常见算术运算符

| 运算符 | 含义   | 示例     | 结果  |
| ------ | ------ | -------- | ----- |
| `+`    | 加法   | `3 + 2`  | `5`   |
| `-`    | 减法   | `5 - 2`  | `3`   |
| `*`    | 乘法   | `3 * 4`  | `12`  |
| `/`    | 除法   | `5 / 2`  | `2.5` |
| `//`   | 整除   | `5 // 2` | `2`   |
| `%`    | 取余   | `5 % 2`  | `1`   |
| `**`   | 幂运算 | `2 ** 3` | `8`   |



### 2. 赋值运算符（常与算术运算结合）

| 运算符 | 含义                 | 示例      | 等价于       |
| ------ | -------------------- | --------- | ------------ |
| `=`    | 赋值                 | `a = 5`   | 将5赋值给a   |
| `+=`   | 加后赋值             | `a += 3`  | `a = a + 3`  |
| `-=`   | 减后赋值             | `a -= 2`  | `a = a - 2`  |
| `*=`   | 乘后赋值             | `a *= 4`  | `a = a * 4`  |
| `/=`   | 除后赋值（保留小数） | `a /= 2`  | `a = a / 2`  |
| `//=`  | 整除后赋值           | `a //= 2` | `a = a // 2` |
| `%=`   | 取余后赋值           | `a %= 3`  | `a = a % 3`  |
| `**=`  | 幂运算后赋值         | `a **= 2` | `a = a ** 2` |



## 三、流程控制

### 1. 条件判断

```python
if x > 0:
    print("正数")
elif x == 0:
    print("零")
else:
    print("负数")
```

### 2. 循环结构

```python
# while 循环
i = 0
while i < 5:
    print(i)
    i += 1

# for 循环
for i in range(5):
    print(i)
    
for i in range(start, stop[, step]):
    print(i)
```

## 四、函数

### 1. 定义与调用

```python
def greet(name):
    print("Hello", name)

greet("Tom")
```

### 2. 默认参数与可变参数

```python
def add(a, b=0):
    return a + b

def total(*args):
    return sum(args)
```



## 五、数据结构

- **列表**（list）

  ```python
  lst = [1, 2, 3]
  lst.append(4)
  print(lst[0])
  ```

- **元组**（tuple，不可变）

  ```python
  t = (1, 2, 3)
  ```
  
- **字典**（dict）

  ```python
  d = {"name": "Tom", "age": 20}
  print(d["name"])
  ```

- **集合**（set）

  ```python
  s = {1, 2, 3}
  s.add(4)
  ```



## 六、类型转换

```python
int("123")     # 字符串 → 整数
str(123)       # 整数 → 字符串
list("abc")    # 字符串 → 列表 ['a', 'b', 'c']
```



## 七、输入与输出

```python
name = input("请输入名字：")
print("你好", name)
```



## 八、文件操作

```python
# 写入文件
with open("test.txt", "w") as f:
    f.write("hello")

# 读取文件
with open("test.txt", "r") as f:
    content = f.read()
    print(content)
```



## 九、异常处理

```python
try:
    x = 1 / 0
except ZeroDivisionError:
    print("除以 0 错误")
finally:
    print("执行结束")
```



## 十、模块与包

```python
import math
print(math.sqrt(9))
```



## 附录：原码 / 反码 / 补码（带符号整数表示）

- **原码**：最高位为符号位（0 正，1 负），剩余位为绝对值
- **反码**：
  - 正数：与原码相同
  - 负数：符号位不变，其他位按位取反
- **补码**：
  - 正数：与原码相同
  - 负数：反码 + 1

| 数值 | 原码（8 位） | 反码       | 补码       |
| ---- | ------------ | ---------- | ---------- |
| +5   | `00000101`   | `00000101` | `00000101` |
| -5   | `10000101`   | `11111010` | `11111011` |

## 练习题

- 打印一个边长位N的正方形

```python
#!/usr/bin/env python3

num = int(input("请输入一个数字，这将打印一个边长位N的正方形"))
for i in range(num,0,-1):
    if i == num or i == 1:
        print ('#'*num)
    else:
        print (f"#{' '*(num-2)}#")
```



- 求100内所有奇数的和

```python
#!/usr/bin/env python3
sum = 0
for i in range(1,101,2):
   sum += i 
print(sum)
```



- 判断学生成绩，成绩等级A~E。其中，90分以上为A，80~89分为'B'，70~79分为'C'，60~69分
  为'D'，60分以下为'E'

```python
#!/usr/bin/env python3
score = int(input("请输入学生成绩（0~100）: "))

if score >= 90:
    print("等级: A")
elif score >= 80:
    print("等级: B")
elif score >= 70:
    print("等级: C")
elif score >= 60:
    print("等级: D")
else:
    print("等级: E")
```



- 求1到5阶乘之和

```python
#!/usr/bin/env python3
num = 0
for i in range(1,6):
    c = 1
    for a in range(1,i+1):
        c *= a
    num += c
print(num)
```



- 给一个数，判断它是否是质数(一个大于1的自然数只能被1和它本身整除)

```python
#!/usr/bin/env python3
num = int(input("请输入一个正整数: "))

if num <= 1:
    print("不是质数")
else:
    for i in range(2, int(num**0.5) + 1):
        if num % i == 0:
            print("这个数不是质数")
            break
    else:
        print("这个数是质数")
```



- 打印九九乘法表

```python
#!/usr/bin/env python3
for i in range(1, 10):
    for j in range(1, i + 1):
        print(f"{j}x{i}={j * i}\t", end='')
    print()
```



- 打印100以内的斐波那契数列，求第101项

```python
#!/usr/bin/env python3
one = -1
two = 1
three = 0
i = 1
while True:
    three = one + two
    if three > 100:
        break
    print(f"第{i}项: {three}")
    one = two
    two = three
    i += 1

#!/usr/bin/env python
one = -1
two = 1
three = 0
for i in range(1, 102):
    three = one + two
    print(f"第{i}项: {three}")
    one = two
    two = three
```



- 求10万以内所有素数

```python
#!/usr/bin/env python3
b = 0
for i in range(2,100001):
    for a in range(2,int(i**0.5)+1):
        if i % a == 0:
            break
    else:
        b += 1
        print(f"第{b}个:{i}")
```



- 打印菱形

```python
     *
    ***
   *****
  *******
   *****
    ***
     *
      
  #!/usr/bin/env python
  for i in range(-3,4,1):
      if i < 0:
          i = i * -1
      print(" " * i + "*" * (7 - ( 2 * i)))
      
--------------------------------------------  
     * 
    **
   ***
  *******
     ***
     **
     *
  
  #!/usr/bin/env python
  for i in range(-3,4):
      if i < 0:
          i = -i
          print(" " * i + "*" * (4 - i))
      elif i == 0:
          print("*" * 7)
      else:
          print(" " * 3 + "*" * (4 - i))  
```

  

- 猴子第一天摘下若干个桃子，当即吃了一半，还不过瘾，又多吃了一个。第二天早上又将剩下的
  桃子吃掉一半，又多吃了一个。以后每天早上都吃了前一天剩下的一半零一个。到第10天早上想
  吃时，只剩下一个桃子了。求第一天共摘多少个桃子。

```python
#!/usr/bin/env python
total=1
for i in range(9,0,-1):
    total = (total + 1) * 2
    print(f"第{i}天, 还剩{total}个桃子")
```

