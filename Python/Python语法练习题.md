## 练习题

#### 1. 打印一个边长位N的正方形

```python
#!/usr/bin/env python3

num = int(input("请输入一个数字，这将打印一个边长位N的正方形"))
for i in range(num,0,-1):
    if i == num or i == 1:
        print ('#'*num)
    else:
        print (f"#{' '*(num-2)}#")
```



#### 2. 求100内所有奇数的和

```python
#!/usr/bin/env python3
sum = 0
for i in range(1,101,2):
   sum += i 
print(sum)
```



#### 3. 判断学生成绩

判断学生成绩，成绩等级A~E。其中，90分以上为A，80~89分为'B'，70~79分为'C'，60~69分

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



#### 4. 求1到5阶乘之和

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



#### 5. 判断是否是质数

给一个数，判断它是否是质数(一个大于1的自然数只能被1和它本身整除)

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



#### 6. 打印九九乘法表

```python
#!/usr/bin/env python3
for i in range(1, 10):
    for j in range(1, i + 1):
        print(f"{j}x{i}={j * i}\t", end='')
    print()
```



#### 7. 斐波那契

打印100以内的斐波那契数列，求第101项

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



#### 8. 求10万以内所有素数

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



#### 9. 打印菱形

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

  

#### 10. 猴子吃桃

第一天摘下若干个桃子，当即吃了一半，还不过瘾，又多吃了一个。第二天早上又将剩下的桃子吃掉一半，又多吃了一个。以后每天早上都吃了前一天剩下的一半零一个。到第10天早上想吃时，只剩下一个桃子了。求第一天共摘多少个桃子。

```python
#!/usr/bin/env python
total=1
for i in range(9,0,-1):
    total = (total + 1) * 2
    print(f"第{i}天, 还剩{total}个桃子")
```



#### 11. 打印杨辉三角形

  ```python
  #!/usr/bin/env python3
  
  total = []
  for i in range(1,7):
  
      lst = []
  
      for j in range(i):
  
          if j == 0 or j == (i-1):
              lst.append(1)
  
          else:
              lst.append(total[i-2][j-1] + total[i-2][j])
  
      total.append(lst)
      print(lst)
  print(total)
  ```

  