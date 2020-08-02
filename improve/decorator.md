#### 66 装饰器极简入门

##### 66.1 定义装饰器

time 模块大家比较清楚，第一个导入 `wraps` 函数（装饰器）为确保被装饰的函数名称等属性不发生改变用的，这点现在不清楚也问题不大，实践一下就知道了。

```python
from functools import wraps
import time
```

定义一个装饰器：print_info，装饰器函数入参要求为函数，返回值要求也为函数。

如下，入参为函数 f, 返回参数 info 也为函数，满足要求。

```python
def print_info(f):
    """
    @para: f, 入参函数名称
    """
    @wraps(f) # 确保函数f名称等属性不发生改变
    def info():
        print('正在调用函数名称为： %s ' % (f.__name__,))
        t1 = time.time()
        f()
        t2 = time.time()
        delta = (t2 - t1)
        print('%s 函数执行时长为：%f s' % (f.__name__,delta))

    return info
```

##### 66.2使用装饰器

使用 print_info 装饰器，分别修饰 f1, f2 函数。

软件工程要求尽量一次定义，多次被复用。

```python
@print_info
def f1():
    time.sleep(1.0)


@print_info
def f2():
    time.sleep(2.0)
```

##### 66.3 使用装饰后的函数

使用 f1, f2 函数：

```python
f1()
f2()

# 输出信息如下：

# 正在调用函数名称为：f1
# f1 函数执行时长为：1.000000 s
# 正在调用函数名称为：f2
# f2 函数执行时长为：2.000000 s
```