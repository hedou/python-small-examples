#### 96 lambda 函数

lambda 函数使用方便，主要由入参和返回值组成，被广泛使用在 max, map, reduce, filter 等函数的 key 参数中。

如下，求 x 中绝对值最大的元素，key 函数确定`abs(x)`作为比较大小的方法：

```python
x = [1, 3, -5]
y = max(x, key=lambda x: abs(x))
print(y) # -5 
```