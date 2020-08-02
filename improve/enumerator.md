#### 86. enumerate 枚举

直接使用 enumerate 枚举容器，第二个参数表示索引的起始值

```python
x = [1, 3, 5]

for i, e in enumerate(x, 10): # 枚举
    print(i, e)
```

下面写法不够 Pythoner:

```python
i = 0

while i < len(x):
    print(i+10, x[i])
    i+=1
```