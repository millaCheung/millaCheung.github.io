---
title: 对Sort()函数的理解（函数引用带括号与不带括号的区别）
date: 2019-10-22 22:58:13
tags:
 - Python
comment: true 
---
**1.sort() 函数用于对原列表进行排序，如果指定参数，则使用比较函数指定的比较函数**

**2.语法 list.sort(key=None, reverse=False)**

**3.参数 key -- 主要是用来进行比较的元素，只有一个参数，具体的函数的参数就是取自于可迭代对象中，指定可迭代对象中的一个元素来进行排序。 <理解：表述元素的权重，如果函数中指定了key，那么就按照key指定的函数list中的元素进行权值从小到大排序> reverse -- 排序规则，reverse = True 降序， reverse = False 升序（默认）**

**4.返回值 该方法没有返回值，但是会对列表的对象进行排序**

<!-- more -->

**5.实例**

```python
aList = ['Google', 'Runoob', 'Taobao', 'Facebook'] 
aList.sort()
print ( "List : ", aList)

# 输出结果：List :  ['Facebook', 'Google', 'Runoob', 'Taobao']
```

```python
def length(x):
    return len(x)

aList = ['Google', 'Runoob', 'Taobao', 'Facebook']
aList.sort(key=length)  # 以下讲解调用函数带括号与不带括号区别
# 该函数中，使用了key参数，可知，排序list中的元素使用length函数进行排序，length函数中返回值为元素的长度，故可知使用元素长度对元素进行排序，
# 故元素Facebook长度最长，排最后，由于其他参数长度相同，故采用默认排序方式进行排序。
print ( "List : ", aList)

# 输出结果：List :  ['Google', 'Runoob', 'Taobao', 'Facebook']
```
上述代码可改写为lambda函数
```python
aList = ['Google', 'Runoob', 'Taobao', 'Facebook']
aList.sort(key=lambda x:len(x))  
print ( "List : ", aList)

# 输出结果：List :  ['Google', 'Runoob', 'Taobao', 'Facebook']
```

```python
vowels = ['e', 'a', 'u', 'o', 'i']
vowels.sort(reverse=True)  # 降序排序
print ( 'result：', vowels )

# 输出结果：result： ['u', 'o', 'i', 'e', 'a']
```

**6.调用函数带括号及不带括号区别**
```python
# 带括号
def fun1():
    return 1

a = fun1()
print(a)

# 输出结果：1
# 输出结果为1，调用函数时带括号，表示该函数的执行结果
```
```python
# 不带括号
def fun2():
    return 1

b = fun2
print(b)

# 输出结果：<function fun2 at 0x00000287B5CA4D90>
# 第二次的输出结果为fun2的内存，表示不带括号调用为调用该函数
```
