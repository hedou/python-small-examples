####  60 with 读写文件

读文件：

```python
>> import os
>>> os.chdir('D:/source/dataset')
>>> os.listdir()
['drinksbycountry.csv', 'IMDB-Movie-Data.csv', 'movietweetings', 'test.csv', 'titanic_eda_data.csv', 'titanic_train_data.csv', 'train.csv']
# 读文件
>>> with open('drinksbycountry.csv',mode='r',encoding='utf-8') as f:
      o = f.read()
      print(o)
```

写文件：

```python
# 写文件
>>> with open('new_file.txt',mode='w',encoding='utf-8') as f:
      w = f.write('I love python\n It\'s so simple')
      os.listdir()

 
['drinksbycountry.csv', 'IMDB-Movie-Data.csv', 'movietweetings', 'new_file.txt', 'test.csv', 'titanic_eda_data.csv', 'titanic_train_data.csv', 'train.csv']
>>> with open('new_file.txt',mode='r',encoding='utf-8') as f:
      o = f.read()
      print(o)
 
I love python
 It's so simple
```

#### 61 提取后缀名

```python
>>> import os
>>> os.path.splitext('D:/source/dataset/new_file.txt')
('D:/source/dataset/new_file', '.txt') #[1]：后缀名
```

#### 62 提取完整文件名

```python
>>> import os
>>> os.path.split('D:/source/dataset/new_file.txt')
('D:/source/dataset', 'new_file.txt')
```