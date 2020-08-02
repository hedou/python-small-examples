#### 71 pyecharts

导入包：

```python
import pyecharts
pyecharts.__version__ # '1.7.1'
```

绘制图（自动打开html）：

```python
bar = (
        Bar()
        .add_xaxis([0, 1, 2, 3, 4, 5])
        .add_yaxis('ybar',[1.5, 1, -1.3, 0.7, 0.8, 0.9])
    )
line = (Line()
        .add_xaxis([0, 1, 2, 3, 4, 5])
        .add_yaxis('yline',[2, 0.5, 0.7, -1.2, 0.3, 0.4])
        )
bar.overlap(line)
bar.render_notebook()
```

![](https://imgkr.cn-bj.ufileos.com/73187e0c-cbb4-495e-8f32-96a80ecf817d.png)