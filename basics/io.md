#### 30 打开文件

返回文件对象

```python
>>> import os
>>> os.chdir('D:/source/dataset')
>>> os.listdir()
['drinksbycountry.csv', 'IMDB-Movie-Data.csv', 'movietweetings', 
'titanic_eda_data.csv', 'titanic_train_data.csv']
>>> o = open('drinksbycountry.csv',mode='r',encoding='utf-8')
>>> o.read()
"country,beer_servings,spirit_servings,wine_servings,total_litres_of_pur
e_alcohol,continent\nAfghanistan,0,0,0,0.0,Asia\nAlbania,89,132,54,4.9,"
```

mode 取值表：

| 字符  | 意义                             |
| :---- | :------------------------------- |
| `'r'` | 读取（默认）                     |
| `'w'` | 写入，并先截断文件               |
| `'x'` | 排它性创建，如果文件已存在则失败 |
| `'a'` | 写入，如果文件存在则在末尾追加   |
| `'b'` | 二进制模式                       |
| `'t'` | 文本模式（默认）                 |
| `'+'` | 打开用于更新（读取与写入）       |

#### 26 获取用户输入　

获取用户输入内容

```python
>>> input()
I'm typing 
"I'm typing "
```