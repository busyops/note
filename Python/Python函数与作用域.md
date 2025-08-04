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

