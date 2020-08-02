#### 94 `__name__ == '__main__'`有啥用

曾几何时，看这别人代码这么写，我们也就跟着这么用吧，其实还没有完全弄清楚这行到底干啥。

```python
def mymain():
    print('Doing something in module', __name__)


if __name__ == '__main__':
    print('Executed from command line')
    mymain()
```

加入上面脚本命名为 MyModule，不管在 vscode 还是 pycharm 直接启动，则直接打印出：

```python
Executed from command line
Doing something in module __main__
```

这并不奇怪，和我们预想一样，因为有无这句 `__main__` ，都会打印出这些。

但是当我们 `import MyModule` 时，如果没有这句，直接就打印出：

```python
In [2]: import MyModule
Executed from command line
Doing something in module MyModule
```

只是导入就直接执行 mymain 函数，这不符合我们预期。

如果有主句，导入后符合预期：

```python
In [6]: import MyModule

In [7]: MyModule.mymain()
Doing something in module MyModule
```