### 1.6 函数

#### 1 求绝对值

绝对值或复数的模

```python
>>> abs(-6)
6
```

#### 19 门牌号　

返回对象的内存地址

```python
>>> class Student():
      def __init__(self,id,name):
        self.id = id
        self.name = name
          
>>> xiaoming = Student('001','xiaoming') 
>>> id(xiaoming)
2281930739080
```

#### 18 查看变量所占字节数

```python
>>> import sys
>>> a = {'a':1,'b':2.0}
>>> sys.getsizeof(a) # 变量占用字节数
240
```



#### 20 排序函数

排序：

```python
>>> a = [1,4,2,3,1]
#降序
>>> sorted(a,reverse=True)
[4, 3, 2, 1, 1]
>>> a = [{'name':'xiaoming','age':18,'gender':'male'},
       {'name':'xiaohong','age':20,'gender':'female'}]
#按 age升序
>>> sorted(a,key=lambda x: x['age'],reverse=False)
[{'name': 'xiaoming', 'age': 18, 'gender': 'male'}, 
{'name': 'xiaohong', 'age': 20, 'gender': 'female'}]
```

#### 21 求和函数

求和：

```python
>>> a = [1,4,2,3,1]
>>> sum(a)
11
#求和初始值为1
>>> sum(a,1)
12
```





#### 29 返回对象哈希值　　

返回对象的哈希值。值得注意，自定义的实例都可哈希：

  ```python
  >>> class Student():
        def __init__(self,id,name):
          self.id = id
          self.name = name
          
>>> xiaoming = Student('001','xiaoming')
>>> hash(xiaoming)
-9223371894234104688
  ```
`list`, `dict`, `set`等可变对象都不可哈希(unhashable)：
```python
>>> hash([1,3,5])
Traceback (most recent call last):
  File "<pyshell#71>", line 1, in <module>
    hash([1,3,5])
TypeError: unhashable type: 'list'
```

#### 41 枚举对象

Python 的枚举对象

```python
>>> s = ["a","b","c"]
>>> for i,v in enumerate(s):
       print(i,v)
0 a
1 b
2 c
```

#### 98 map

map 函数映射 fun 到容器中每个元素，并返回迭代器 x

```python
x = map(str, [1, 3, 5])
for e in x:
    print(e, type(e))
```

下面写法不够 Pythoner

```python
for e in [1, 3, 5]:
    print(e, str(e)) # '1','3','5'
```

#### 99 reduce

reduce 是在 functools 中，第一个参数是函数，其必须含有 2 个参数，最后归约为一个标量。

```python
from functools import reduce
x = [1, 3, 5]
y = reduce(lambda p1, p2: p1*p2, x)
print(y) # 15
```

下面写法不够 Pythoner:

```python
y = 1
for e in x:
    y *= e
print(y)
```

#### 97 max

求 x 中绝对值最大的元素，key 函数确定`abs(x)`作为比较大小的方法：

```python
x = [1, 3, -5]
y = max(x, key=lambda x: abs(x))
print(y) # -5 
```

