#### 69 seaborn

导入包：

```python
import seaborn as sns 
sns.__version__ # '0.8.0'
```

绘制图：

```python
sns.barplot([0, 1, 2, 3, 4, 5],
        [1.5, 1, -1.3, 0.7, 0.8, 0.9]
        )
sns.pointplot([0, 1, 2, 3, 4, 5],
        [2, 0.5, 0.7, -1.2, 0.3, 0.4]
        )
plt.show()
```

![](https://imgkr.cn-bj.ufileos.com/bf460045-a7da-4679-92d3-8e7f2a951b3f.png)