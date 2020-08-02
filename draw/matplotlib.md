#### 68 matplotlib

导入包：

```python
import matplotlib 
matplotlib.__version__  # '2.2.2'

import matplotlib.pyplot as plt
```

绘图代码：

```python
import matplotlib.pyplot as plt 
plt.plot([0, 1, 2, 3, 4, 5],
        [1.5, 1, -1.3, 0.7, 0.8, 0.9]
        ,c='red')
plt.bar([0, 1, 2, 3, 4, 5],
        [2, 0.5, 0.7, -1.2, 0.3, 0.4]
        )
plt.show()
```

![](https://imgkr.cn-bj.ufileos.com/a27c0f2c-1d0c-4228-97e0-7f311e0b4b96.png)