### 1.8 数据结构

#### 8 转为字典　　

创建数据字典的几种方法

```python
>>> dict()
{}
>>> dict(a='a',b='b')
{'a': 'a', 'b': 'b'}
>>> dict(zip(['a','b'],[1,2]))
{'a': 1, 'b': 2}
>>> dict([('a',1),('b',2)])
{'a': 1, 'b': 2}
```

#### 11  转为集合

返回一个 set 对象，集合内不允许有重复元素：

```python
>>> a = [1,4,2,3,1]
>>> set(a)
{1, 2, 3, 4}
```

#### 12 转为切片

*class* slice(*start*, *stop*[, *step*])

返回一个由 range(start, stop, step) 指定索引集的 slice 对象，代码可读性变好。

```python
>>> a = [1,4,2,3,1]
>>> my_slice = slice(0,5,2)
>>> a[my_slice]
[1, 2, 1]
```

#### 13 转元组

 `tuple()` 将对象转为一个不可变的序列类型

 ```python
>>> a=[1,3,5]
>>> a.append(7)
>>> a
[1, 3, 5, 7]
#禁止a增删元素，只需转为元组
>>> t=tuple(a)
>>> t
(1, 3, 5, 7)
 ```

#### 14 转冻结集合　　

创建不可修改的集合：

```python
>>> a = frozenset([1,1,3,2,3])
>>> a # a 无 pop,append,insert等方法
frozenset({1, 2, 3})
```

#### 95 字典默认值

```python
In[1]: d = {'a': 1, 'b': 3}

In[2]: d.get('b', [])  # 存在键 'b'
Out[2]: 3

In[3]: d.get('c', [])  # 不存在键 'c'，返回[]
Out[3]: []
```