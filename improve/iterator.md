#### 43 创建range迭代器

1. range(stop)
2. range(start, stop[,step])

生成一个不可变序列的迭代器：

```python
>>> t = range(11)
>>> t = range(0,11,2)
>>> for e in t:
     print(e)

0
2
4
6
8
10
```

#### 45 打包迭代器

聚合各个可迭代对象的迭代器：

```python
>>> x = [3,2,1]
>>> y = [4,5,6]
>>> list(zip(y,x))
[(4, 3), (5, 2), (6, 1)]
>>> for i,j in zip(y,x):
 print(i,j)

4 3
5 2
6 1
```


#### 42 创建迭代器

```python
>>> class TestIter():
 def __init__(self,lst):
  self.lst = lst
  
 # 重写可迭代协议__iter__
 def __iter__(self):
  print('__iter__ is called')
  return iter(self.lst)
```

迭代 TestIter 类：

```python
>>> t = TestIter()
>>> t = TestIter([1,3,5,7,9])
>>> for e in t:
 print(e)

 
__iter__ is called
1
3
5
7
9
```



#### 44 反向迭代器

```python
>>> rev = reversed([1,4,2,3,1])
>>> for i in rev:
 print(i)
 
1
3
2
4
1
```


#### 46 过滤器

函数通过 lambda 表达式设定过滤条件，保留 lambda 表达式为`True`的元素：

```python
>>> fil = filter(lambda x: x>10,[1,11,2,45,7,6,13])
>>> for e in fil:
       print(e)

11
45
13
```

#### 100 filter

使用 filter 找到满足 key 函数指定条件的元素，并返回迭代器

如下，使用 filter 找到所有奇数：

```python
x = [1, 2, 3, 5]
odd = filter(lambda e: e % 2, x)
for e in odd:  # 找到奇数
    print(e)
```

还有另外一种方法，使用列表生成式，直接得到一个odd 容器，

```python
odd = [e for e in x if e % 2]
print(odd) # [1,3,5]
```

下面写法最不符合 Python 习惯：

```python
odd = []
for e in x:
    if e % 2:
        odd.append(e)
print(odd)  # [1,3,5]
```

#### 67 迭代器案例

一个类如何成为迭代器类型，请看官方PEP说明：

![](https://imgkr.cn-bj.ufileos.com/814ef236-5015-409e-bdf0-3a73ca092d86.png)

即必须实现两个方法（或者叫两种协议）：`__iter__` , `__next__`

下面编写一个迭代器类：

```python
class YourRange():
    def __init__(self, start, end):
        self.value = start
        self.end = end

    # 成为迭代器类型的关键协议
    def __iter__(self):
        return self

    # 当前迭代器状态(位置)的下一个位置
    def __next__(self):
        if self.value >= self.end:
            raise StopIteration

        cur = self.value
        self.value += 1
        return cur
```

使用这个迭代器：

```python
yr = YourRange(5, 12)
for e in yr:
    print(e)
```

迭代器实现`__iter__` 协议，它就能在 for 上迭代，参考官网PEP解释：

![](https://imgkr.cn-bj.ufileos.com/21a4e587-788e-4343-82c4-9d004e54f962.png)

文章最后提个问题，如果此时运行：

```python
next(yr)
```

会输出 5， 还是报错？

如果 yr 是 list，for 遍历后，再 next(iter(yr)) 又会输出什么？

如果能分清这些问题，恭喜你，已经真正理解迭代器迭代和容器遍历的区别。如果你还拿不准，欢迎交流。