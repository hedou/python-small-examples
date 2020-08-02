
![完整施工计划](https://static01.imgkr.com/temp/a17e23e969af4439becbff3b91da4bf7.png)


作为开篇，简要总结下`Python`语言：

Python语言`1989`年由 `Guido van Rossum` 编写，一名荷兰籍程序员：

![](https://static01.imgkr.com/temp/0608b3f17349432bb7296dcb1628fa2d.png)


Python可以应用在众多的`领域`中：

数据分析、组件集成、网络服务、图像处理、数值计算和科学计算等领域。

Python应用的`知名公司`有：

Youtube、Dropbox、BT、知乎、豆瓣、谷歌、百度、腾讯、汽车之家等。

Python可以做的`工作`有：

自动化运维、测试、机器学习、深度学习、数据分析、爬虫、Web等

通常使用最广泛的是`CPython`编译器，它将源文件（py文件）转换成字节码文件（pyc文件），然后运行在Python虚拟机上。


![数字总结导图](https://static01.imgkr.com/temp/038a8ae58477452c9cac2fd6499ddb13.png)

数字

- 整数
	- Python2 有取值范围，溢出后自动转为长整型
	- **Python3 中为长整型，无位数限制 理论上内存有多大，位数可能就有多大**
- 长整数
	- Python2 中单独对应 Long 类型
	- Python3 中不再有Long ，直接对应 int
- 浮点数
	- 带小数的数字
	- 如果不带数字，可能有 e 和 E
- 复数
	- 高数中复数
	- 结构为：1+2j



下面是常用的数字相关的操作：



#### 1 / 返回浮点数

即便两个整数，`/` 操作也会返回浮点数
```python
In [1]: 8/5
Out[1]: 1.6
```

#### 2 // 得到整数部分

使用 `//`快速得到两数相除的整数部分，并且返回整型，此操作符容易忽略，但确实很实用。

```python
In [2]: 8//5
Out[2]: 1

In [3]: a = 8//5
In [4]: type(a)
Out[4]: int
```

#### 3 % 得到余数

`% ` 得到两数相除的余数：

```python
In [6]: 8%5
Out[6]: 3
```

#### 4 ** 计算乘方

`**` 计算几次方
```python
In [7]: 2**3
Out[7]: 8
```

#### 5 交互模式下的_

在交互模式下，上一次打印出来的表达式被赋值给变量  `_`
```python
In [8]: 2*3.02+1
Out[8]: 7.04

In [9]: 1+_
Out[9]: 8.04
```

#### 6  十转二

将十进制转换为二进制：

```python
>>> bin(10)
'0b1010'
```

#### 7 十转八

十进制转换为八进制：

```python
>>> oct(9)
'0o11'
```

#### 8 十转十六

十进制转换为十六进制：

```python
>>> hex(15)
'0xf'
```

#### 9 转为浮点类型　

整数或数值型字符串转换为浮点数

```python
>>> float(3)
3.0
```

如果不能转化为浮点数，则会报 `ValueError`:

```python
>>> float('a')
Traceback (most recent call last):
  File "<pyshell#7>", line 1, in <module>
    float('a')
ValueError: could not convert string to float: 'a'
```

#### 10  转为整型　　

int(x, base =10) 

x 可能为字符串或数值，将 x 转换为整数：

```python
>>> int('12',16)
18
```

#### 11 商和余数　　

分别取商和余数

```python
>>> divmod(10,3)
(3, 1)
```

#### 12 幂和余同时做

pow 三个参数都给出，表示先幂运算再取余：

```python
>>> pow(3, 2, 4)
1
```

#### 13 四舍五入

四舍五入，第二个参数代表小数点后保留几位：

```python
>>> round(10.045, 2)
10.04
>>> round(10.046, 2)
10.05
```

#### 14  计算表达式

使用内置函数`eval`计算字符串型表达式的值：

```python
>>> s = "1 + 3 +5"
>>> eval(s)
9
>>> eval('[1,3,5]*3')
[1, 3, 5, 1, 3, 5, 1, 3, 5]
```

真假布尔值本质上也是数字，所以也归并到此节中讨论。

#### 15 真假　

以下四种情况都为假值：

![](https://static01.imgkr.com/temp/3dccf0a6cd45413aa6ea588525272709.png)

```python
>>> bool(0)
False
>>> bool(False)
False
>>> bool(None)
False
>>> bool([])
False
```

以下这些情况为真：

```python
>>> bool([False])
True
>>> bool([0,0,0])
True
```

#### 16 all 判断元素是否都为真

所有元素都为真返回 `True`，否则返回`False`
```python
#有0，所以不是所有元素都为真
>>> all([1,0,3,6])
False
```

```python
#所有元素都为真
>>> all([1,2,3])
True
```

#### 17 any 判断是否至少有一个元素为真

至少有一个元素为真返回`True`，否则返回`False`


```python
# 没有一个元素为真
>>> any([0,0,0,[]])
False
```

```python
# 至少一个元素为真
>>> any([0,0,1])
True
```

#### 18 链式比较

Python 支持下面这种链式比较，非常方便：

```python
>>> i = 3
>>> 1 < i < 3
False
>>> 1 < i <=3
True
```

#### 19 交换元素

Python 除了支持上面的链式比较外，还支持一种更加方便的操作：直接解包赋值。

如下所示，1,3 解包后分别赋值给a, b ，利用此原理一行代码实现两个数字的直接交换。

```python
a, b = 1, 3
a, b = b, a  # 交换 a,b
```

如果明白此原理，下面的赋值操作就会迎刃而解：

```python
a,b = 1, 3
a, b = b+1, a-1
print(a,b) # 结果是多少？
```

可能会有疑问：是 b+1 赋值给 a 后，a-1再赋值给 b ？

如果明白了上面的原理：等号右面完成压包，左侧再解包。

就会立即得出答案：肯定不是。

下面这行代码：

```python
a, b = b+1, a-1
```

等价于：

```python
c = b+1, a-1 # 压包
a, b = c # 解包
```

答案是：a=4, b=0

压包和解包还有更加复杂的用法，放到后面进阶部分总结。

#### 20  链式操作

下面这个例子使用 operator 模块中 add, sub 函数，根据操作符+，-，生成对应的函数，然后直接调用。

很像设计模式中最频繁使用的对象工厂模式。

```python
>>> from operator import (add, sub)
>>> def add_or_sub(a, b, oper):
 return (add if oper == '+' else sub)(a, b)
>>> add_or_sub(1, 2, '-')
-1
```

版权归《Python小例子》所有：

![](https://static01.imgkr.com/temp/4bece9e333604b0095f878cfc820192f.png)