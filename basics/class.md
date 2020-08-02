#### 31 查看对象类型

*class* type(*name*, *bases*, *dict*)

传入参数，返回 *object* 类型：

```python
>>> type({4,6,1})
<class 'set'>
>>> type({'a':[1,2,3],'b':[4,5,6]})
<class 'dict'>
>>> class Student():
      def __init__(self,id,name):
        self.id = id
        self.name = name

>>> type(Student('1','xiaoming'))
<class '__main__.Student'>
```

#### 32  两种创建属性方法

返回 property 属性，典型的用法：

```python
>>> class C:
    def __init__(self):
      self._x = None
    def getx(self):
      return self._x
    def setx(self, value):
      self._x = value
    def delx(self):
      del self._x
    # 使用property类创建 property 属性
    x = property(getx, setx, delx, "I'm the 'x' property.")
```
使用 C 类：
```python	
>>> C().x=1
>>> c=C()
# 属性x赋值
>>> c.x=1
# 拿值
>>> c.getx()
1
# 删除属性x
>>> c.delx()
# 再拿报错
>>> c.getx()
Traceback (most recent call last):
  File "<pyshell#118>", line 1, in <module>
    c.getx()
  File "<pyshell#112>", line 5, in getx
    return self._x
AttributeError: 'C' object has no attribute '_x'
# 再属性赋值
>>> c.x=1
>>> c.setx(1)
>>> c.getx()
1
```

使用`@property`装饰器，实现与上完全一样的效果：

```python
class C:
    def __init__(self):
        self._x = None

    @property
    def x(self):
        return self._x

    @x.setter
    def x(self, value):
        self._x = value

    @x.deleter
    def x(self):
        del self._x
```

#### 33 是否可调用　　

判断对象是否可被调用，能被调用的对象是一个`callable` 对象。

```python
>>> callable(str)
True
>>> callable(int)
True
```
Student 对象实例目前不可调用：

```python
>>> class Student():
        def __init__(self,id,name):
            self.id = id
            self.name = name

>>> xiaoming = Student(id='1',name='xiaoming')
>>> callable(xiaoming)
False
```

如果 `xiaoming`能被调用 , 需要重写`Student`类的`__call__`方法：

```python
>>> class Student():
      def __init__(self,id,name):
        self.id = id
        self.name = name
      def __call__(self):
        print('I can be called')
        print(f'my name is {self.name}')
```
此时调用 xiaoming():

```python
>>> xiaoming = Student('001','xiaoming')
>>> xiaoming()
I can be called
my name is xiaoming
```

#### 34 动态删除属性　　

删除对象的属性

```python
>>> class Student():
      def __init__(self,id,name):
        self.id = id
        self.name = name

>>> xiaoming = Student('001','xiaoming')
>>> delattr(xiaoming,'id')
>>> hasattr(xiaoming,'id')
False
```

#### 35 动态获取对象属性　

获取对象的属性

```python
>>> class Student():
      def __init__(self,id,name):
        self.id = id
        self.name = name
       
>>> xiaoming = Student('001','xiaoming')
>>> getattr(xiaoming,'name') # 获取name的属性值
'xiaoming'
```

#### 36 对象是否有某个属性

```python
>>> class Student():
      def __init__(self,id,name):
        self.id = id
        self.name = name
        
>>> xiaoming = Student('001','xiaoming')        
>>> getattr(xiaoming,'name')# 判断 xiaoming有无 name属性
'xiaoming'
>>> hasattr(xiaoming,'name')
True
>>> hasattr(xiaoming,'address')
False
```

#### 37 isinstance

判断*object*是否为*classinfo*的实例，是返回true

```python
>>> class Student():
      def __init__(self,id,name):
        self.id = id
        self.name = name
       
>>> xiaoming = Student('001','xiaoming')
>>> isinstance(xiaoming,Student)
True
```

#### 38 父子关系鉴定

```python
>>> class Student():
      def __init__(self,id,name):
        self.id = id
        self.name = name
        
>>> class Undergraduate(Student): 
       pass
        
# 判断 Undergraduate 类是否为 Student 的子类 
>>> issubclass(Undergraduate,Student)
True
```

第二个参数可为元组：

```python
>>> issubclass(int,(int,float))
True
```

#### 39 所有对象之根

object 是所有类的基类

```python
>>> isinstance(1,object)
True

>>> isinstance([],object)
True
```

####  40 一键查看对象所有方法

不带参数时返回`当前范围`内的变量、方法和定义的类型列表；带参数时返回`参数`的属性，方法列表。

```python
>>> class Student():
      def __init__(self,id,name):
        self.id = id
        self.name = name

>>> xiaoming = Student('001','xiaoming')
>>> dir(xiaoming)
['__call__', '__class__', '__delattr__', '__dict__', '__dir__', '__doc__', '__eq__', '__format__', '__ge__', '__getattribute__', '__gt__', '__hash__', '__init__', '__init_subclass__', '__le__', '__lt__', '__module__', '__ne__', '__new__', '__reduce__', '__reduce_ex__', '__repr__', '__setattr__', '__sizeof__', '__str__', '__subclasshook__', '__weakref__', 'id', 'name']
```