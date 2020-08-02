#### 52 使用time模块打印当前时间

```python
# 导入time模块
>>> import time
# 打印当前时间，返回浮点数
>>> seconds = time.time()
>>> seconds
1588858156.6146255
```

#### 53 浮点数转时间结构体

```python
# 浮点数转时间结构体
>>> local_time = time.localtime(seconds)
>>> local_time
time.struct_time(tm_year=2020, tm_mon=5, tm_mday=7, tm_hour=21, tm_min=29, tm_sec=16, tm_wday=3, tm_yday=128, tm_isdst=0)
```

- tm_year: 年
- tm_mon: 月
- tm_mday: 日
- tm_hour: 小时
- tm_min：分
- tm_sec: 分
- tm_sec: 秒
- tm_wday: 一周中索引([0,6], 周一的索引:0)
- tm_yday: 一年中索引([1,366])
- tm_isdst: 1 if summer time is in effect, 0 if not, and -1 if unknown

#### 54 时间结构体转时间字符串

```python
# 时间结构体转时间字符串
>>> str_time = time.asctime(local_time)
>>> str_time
'Thu May  7 21:29:16 2020'
```

#### 55 时间结构体转指定格式时间字符串

```python
# 时间结构体转指定格式的时间字符串
>>> format_time = time.strftime('%Y.%m.%d %H:%M:%S',local_time)
>>> format_time
'2020.05.07 21:29:16'
```

#### 56 时间字符串转时间结构体

```python
# 时间字符串转时间结构体
>>> time.strptime(format_time,'%Y.%m.%d %H:%M:%S')
time.struct_time(tm_year=2020, tm_mon=5, tm_mday=7, tm_hour=21, tm_min=29, tm_sec=16, tm_wday=3, tm_yday=128, tm_isdst=-1)
```

#### 57 年的日历图

```python
>>> import calendar
>>> from datetime import date
>>> mydate=date.today()
>>> calendar.calendar(2020)
```

结果：

```python
                                  2020

      January                   February                   March        
Mo Tu We Th Fr Sa Su      Mo Tu We Th Fr Sa Su      Mo Tu We Th Fr Sa Su
       1  2  3  4  5                      1  2                         1
 6  7  8  9 10 11 12       3  4  5  6  7  8  9       2  3  4  5  6  7  8
13 14 15 16 17 18 19      10 11 12 13 14 15 16       9 10 11 12 13 14 15
20 21 22 23 24 25 26      17 18 19 20 21 22 23      16 17 18 19 20 21 22
27 28 29 30 31            24 25 26 27 28 29         23 24 25 26 27 28 29
                                                    30 31

       April                      May                       June
Mo Tu We Th Fr Sa Su      Mo Tu We Th Fr Sa Su      Mo Tu We Th Fr Sa Su
       1  2  3  4  5                   1  2  3       1  2  3  4  5  6  7
 6  7  8  9 10 11 12       4  5  6  7  8  9 10       8  9 10 11 12 13 14
13 14 15 16 17 18 19      11 12 13 14 15 16 17      15 16 17 18 19 20 21
20 21 22 23 24 25 26      18 19 20 21 22 23 24      22 23 24 25 26 27 28
27 28 29 30               25 26 27 28 29 30 31      29 30

        July                     August                  September
Mo Tu We Th Fr Sa Su      Mo Tu We Th Fr Sa Su      Mo Tu We Th Fr Sa Su
       1  2  3  4  5                      1  2          1  2  3  4  5  6
 6  7  8  9 10 11 12       3  4  5  6  7  8  9       7  8  9 10 11 12 13
13 14 15 16 17 18 19      10 11 12 13 14 15 16      14 15 16 17 18 19 20
20 21 22 23 24 25 26      17 18 19 20 21 22 23      21 22 23 24 25 26 27
27 28 29 30 31            24 25 26 27 28 29 30      28 29 30
                          31

      October                   November                  December
Mo Tu We Th Fr Sa Su      Mo Tu We Th Fr Sa Su      Mo Tu We Th Fr Sa Su
          1  2  3  4                         1          1  2  3  4  5  6
 5  6  7  8  9 10 11       2  3  4  5  6  7  8       7  8  9 10 11 12 13
12 13 14 15 16 17 18       9 10 11 12 13 14 15      14 15 16 17 18 19 20
19 20 21 22 23 24 25      16 17 18 19 20 21 22      21 22 23 24 25 26 27
26 27 28 29 30 31         23 24 25 26 27 28 29      28 29 30 31
                          30
```

#### 58 月的日历图

```python
>>> import calendar
>>> from datetime import date
>>> mydate = date.today()
>>> calendar.month(mydate.year, mydate.month)
```

结果：

```python
      May 2020
Mo Tu We Th Fr Sa Su
             1  2  3
 4  5  6  7  8  9 10
11 12 13 14 15 16 17
18 19 20 21 22 23 24
25 26 27 28 29 30 31
```

#### 59 判断是否为闰年

```python
>>> import calendar
>>> from datetime import date
>>> mydate = date.today()
>>> is_leap = calendar.isleap(mydate.year)
>>> ("{}是闰年" if is_leap else "{}不是闰年\n").format(mydate.year)
'2020是闰年'
```