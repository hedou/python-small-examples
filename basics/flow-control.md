### 4 流程控制

#### 10 for 和 else

一般语言 *else* 只能和 if 搭，Python 中却支持 for 和 else, try 和 else.

for 和 else 搭后，遍历结束便会执行 else

```python
In [29]: for i in range(3):
    ...:     for j in range(i):
    ...:         print(j)
    ...:     else:
    ...:         print('第%d轮遍历结束\n'%(i+1,))
    ...:
第1轮遍历结束

0
第2轮遍历结束

0
1
第3轮遍历结束
```

#### 85. if not x

直接使用 x 和 not x 判断 x 是否为 None 或空

```python
x = [1,3,5]

if x:
    print('x is not empty ')

if not x:
    print('x is empty')
```

下面写法不够 Pythoner

```python
if x and len(x) > 0:
    print('x is not empty ')

if x is None or len(x) == 0:
    print('x is empty')
```

#### 87. in

判断字符串是否包含某个子串，使用`in`明显更加可读：

```python
x = 'zen_of_python'
if 'zen' in x:
    print('zen is in')
```

find 返回值 要与 -1 判断，不太符合习惯：

```python
if x.find('zen') != -1:
    print('zen is in')
```