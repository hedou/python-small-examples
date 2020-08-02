#### 70 plotly 绘图

导入包：

```python
import plotly 
plotly.__version__ # '2.0.11'
```

绘制图（自动打开html）：

```python
import plotly.graph_objs as go
import plotly.offline as offline

pyplt = offline.plot
sca = go.Scatter(x=[0, 1, 2, 3, 4, 5],
             y=[1.5, 1, -1.3, 0.7, 0.8, 0.9]
            )
bar = go.Bar(x=[0, 1, 2, 3, 4, 5],
            y=[2, 0.5, 0.7, -1.2, 0.3, 0.4]
            )
fig = go.Figure(data = [sca,bar])
pyplt(fig)
```

![](https://imgkr.cn-bj.ufileos.com/8676b74a-13e8-4480-b57c-107746dc15a9.png)