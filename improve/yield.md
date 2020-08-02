#### 63 斐波那契数列前n项

```python
>>> def fibonacci(n):
      a, b = 1, 1
      for _ in range(n):
        yield a
        a, b = b, a+b # 注意这种赋值

>>> for fib in fibonacci(10):
      print(fib)

 
1
1
2
3
5
8
13
21
34
55
```

#### 64 list 等分 n 组

```python
>>> from math import ceil
>>> def divide_iter(lst, n):
      if n <= 0:
        yield lst
        return
      i, div = 0, ceil(len(lst) / n)
      while i < n:
        yield lst[i * div: (i + 1) * div]
        i += 1

  
>>> for group in divide_iter([1,2,3,4,5],2):
      print(group)

 
[1, 2, 3]
[4, 5]
```

#### 65 yield 解释

有好几位同学问我，生成器到底该怎么理解。

在这里我总结几句话，看看是否对不理解生成器的朋友有帮助。

生成器首先是一个 “特殊的” return ，遇到 yield 立即中断返回。

但是，又与 return 不同，yield 后下一次执行会进入到yield 的下一句代码，而不像 return 下一次执行还是从函数体的第一句开始执行。

可能还是没说清，那就用图解释一下：

第一次 yield 返回 1

![](https://imgkr.cn-bj.ufileos.com/a584d400-b41e-4cb7-ab07-a97bbf6d8474.png)

 第二次迭代，直接到位置 2 这句代码：

![](https://imgkr.cn-bj.ufileos.com/d2231554-6356-4cba-925b-b6d4061c4ec1.png)



然后再走 for ,再 yield ，重复下去，直到for结束。

以上就是理解 yield 的重点一个方面。