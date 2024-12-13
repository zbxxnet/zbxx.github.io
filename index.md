## abs()
abs() 返回数字的绝对值。
```python
>>> abs(-7)
7
>>> abs(7)
7
```
## all()
all() 将容器作为参数。如果 python 可迭代对象中的所有值都是 True ，则此函数返回 True。空值为 False。
```python
>>> all({'*','',''})
False
>>> all([' ',' ',' '])
True
```
## any()
如果可迭代对象中的任意一个值为 True，则此函数返回 True。。
```python
>>> any((1,0,0))
True
>>> any((0,0,0))
False
```
## ascii()
返回一个表示对象的字符串。
```python
>>> ascii('ș')
“‘\u0219′”
>>> ascii('ușor')
“‘u\u0219or'”
>>> ascii(['s','ș'])
“[‘s’, ‘\u0219’]”
```
## bin()
将整数转换为二进制字符串。不能将其应用于浮点数。
```python
>>> bin(7)
‘0b111’
>>> bin(7.0)
Traceback (most recent call last):File “<pyshell#20>”, line 1, in <module>
bin(7.0)
TypeError: ‘float’ object cannot be interpreted as an integer
```
## bool()
bool() 将值转换为布尔值。
```python
>>> bool(0.5)
True
>>> bool('')
False
>>> bool(True)
True
```
## bytearray()
bytearray() 返回给定大小的 python 新字节数组。
```python
>>> a=bytearray(4)
>>> a
bytearray(b’\x00\x00\x00\x00′)
>>> a.append(1)
>>> a
bytearray(b’\x00\x00\x00\x00\x01′)
>>> a[0]=1
>>> a
bytearray(b’\x01\x00\x00\x00\x01′)
>>> a[0]
1
```
可以处理列表。
```python
>>> bytearray([1,2,3,4])
bytearray(b’\x01\x02\x03\x04′)
```
## bytes()
bytes()返回一个不可变的字节对象。
```python
>>> bytes(5)
b’\x00\x00\x00\x00\x00′
>>> bytes([1,2,3,4,5])
b’\x01\x02\x03\x04\x05′
>>> bytes('hello','utf-8')
b’hello’Here, utf-8 is the encoding.
```
bytearray() 是可变的，而 bytes() 是不可变的。
```python
>>> a=bytes([1,2,3,4,5])
>>> a
b’\x01\x02\x03\x04\x05′
>>> a[4]= 3
Traceback (most recent call last):
File “<pyshell#46>”, line 1, in <module>
a[4]=3
TypeError: ‘bytes’ object does not support item assignment
Let’s try this on bytearray().
>>> a=bytearray([1,2,3,4,5])
>>> a
bytearray(b’\x01\x02\x03\x04\x05′)
>>> a[4]=3
>>> a
bytearray(b’\x01\x02\x03\x04\x03′)
```
## callable()
callable() 用于检查一个对象是否是可调用的。
```python
>>> callable([1,2,3])
False
>>> callable(callable)
True
>>> callable(False)
False
>>> callable(list)
True
```
## chr()
chr() 用一个范围在（0～255）整数作参数(ASCII)，返回一个对应的字符。
```python
>>> chr(65)
‘A’
>>> chr(97)
‘a’
>>> chr(9)
‘\t’
>>> chr(48)
‘0’
```
## classmethod()
classmethod() 返回函数的类方法。
```python
>>> class hello:
    def sayhi(self):
        print("Hello World!")
        
>>> hello.sayhi=classmethod(hello.sayhi)
>>> hello.sayhi()
Hello World!
```
当我们将方法 sayhi() 作为参数传递给 classmethod() 时，它会将其转换为属于该类的 python 类方法。
然后，我们调用它，就像我们在 python 中调用静态方法一样。

## compile()
compile() 将一个字符串编译为字节代码。
```python
>>> exec(compile('a=5\nb=7\nprint(a+b)','','exec'))
12
```
## complex()
complex() 创建转换为复数。
```python
>>> complex(3)
(3+0j)
>>> complex(3.5)
(3.5+0j)
>>> complex(3+5j)
(3+5j)
```
## delattr()
delattr() 用于删除类的属性。
```python
>>> class fruit:
        size=7  
>>> orange=fruit()
>>> orange.size
7
>>> delattr(fruit,'size')
>>> orange.size
Traceback (most recent call last):File “<pyshell#95>”, line 1, in <module>
orange.size
AttributeError: ‘fruit’ object has no attribute ‘size’
```
## dict()
dict() 用于创建一个字典。
```python
>>> dict()
{}
>>> dict([(1,2),(3,4)])
{1: 2, 3: 4}
```
## dir()
dir() 返回对象的属性。
```python
>>> class fruit:
        size=7
        shape='round'
>>> orange=fruit()
>>> dir(orange)
[‘__class__’, ‘__delattr__’, ‘__dict__’, ‘__dir__’, ‘__doc__’, ‘__eq__’, ‘__format__’, ‘__ge__’, ‘__getattribute__’, ‘__gt__’, ‘__hash__’, ‘__init__’, ‘__init_subclass__’, ‘__le__’, ‘__lt__’, ‘__module__’, ‘__ne__’, ‘__new__’, ‘__reduce__’, ‘__reduce_ex__’, ‘__repr__’, ‘__setattr__’, ‘__sizeof__’, ‘__str__’, ‘__subclasshook__’, ‘__weakref__’, ‘shape’, ‘size’]
```
## divmod()
divmod() 把除数和余数运算结果结合起来，返回一个包含商和余数的元组。
```python
>>> divmod(3,7)
(0, 3)
>>> divmod(7,3)
(2, 1)
```
## enumerate()
用于将一个可遍历的数据对象(如列表、元组或字符串)组合为一个索引序列，同时列出数据和数据下标，一般用在 for 循环当中。
```python
>>> for i in enumerate(['a','b','c']):
        print(i)
(0, ‘a’) (1, ‘b’) (2, ‘c’)
```
## eval()
用来执行一个字符串表达式，并返回表达式的值。
字符串表达式可以包含变量、函数调用、运算符和其他 Python 语法元素。
```python
>>> x=7
>>> eval('x+7')
14
>>> eval('x+(x%2)')
8
```
## exec()
exec() 动态运行 Python 代码。
```python
>>> exec('a=2;b=3;print(a+b)')
5
>>> exec(input("Enter your program"))
Enter your programprint
```
## filter()
过滤掉条件为True的项目。
```python
>>> list(filter(lambda x:x%2==0,[1,2,0,False]))
[2, 0, False]
```
## float()
转换为浮点数。
```python
>>> float(2)
2.0
>>> float('3')
3.0
>>> float('3s')
Traceback (most recent call last):File “<pyshell#136>”, line 1, in <module>
float(‘3s’)
ValueError: could not convert string to float: ‘3s’
>>> float(False)
0.0
>>> float(4.7)
4.7
```
## format()
格式化输出字符串。
```python
>>> a,b=2,3
>>> print("a={0} and b={1}".format(a,b))
a=2 and b=3
>>> print("a={a} and b={b}".format(a=3,b=4))
a=3 and b=4
```
## frozenset()
frozenset() 返回一个冻结的集合，冻结后集合不能再添加或删除任何元素。
```python
>>> frozenset((3,2,4))
frozenset({2, 3, 4})
```
## getattr()
getattr() 返回对象属性的值。
```python
>>> getattr(orange,'size')
7
```

## globals()
以字典类型返回当前位置的全部全局变量。
```python
>>> globals()
{‘__name__’: ‘__main__’, ‘__doc__’: None, ‘__package__’: None, ‘__loader__’: <class ‘_frozen_importlib.BuiltinImporter’>, ‘__spec__’: None, ‘__annotations__’: {}, ‘__builtins__’: <module ‘builtins’ (built-in)>, ‘fruit’: <class ‘__main__.fruit’>, ‘orange’: <__main__.fruit object at 0x05F937D0>, ‘a’: 2, ‘numbers’: [1, 2, 3], ‘i’: (2, 3), ‘x’: 7, ‘b’: 3}
```
## hasattr()
用于判断对象是否包含对应的属性。
```python
>>> hasattr(orange,'size')
True
>>> hasattr(orange,'shape')
True
>>> hasattr(orange,'color')
False
```
## hash()
hash() 返回对象的哈希值。
```python
>>> hash(orange)
6263677
>>> hash(orange)
6263677
>>> hash(True)
1
>>> hash(0)
0
>>> hash(3.7)
644245917
>>> hash(hash)
25553952
```
## help()
获取有关任何模块、关键字、符号或主题的详细信息。
```python
>>> help()
Welcome to Python 3.7's help utility!
If this is your first time using Python, you should definitely check out the tutorial on the Internet at https://docs.python.org/3.7/tutorial/.
Enter the name of any module, keyword, or topic to get help on writing Python programs and using Python modules. To quit this help utility and return to the interpreter, just type "quit".
To get a list of available modules, keywords, symbols, or topics, type "modules", "keywords", "symbols", or "topics". Each module also comes with a one-line summary of what it does; to list the modules whose name or summary contain a given string such as "spam", type "modules spam".
help> map Help on class map in module builtins:
class map(object) | map(func, iterables) --> map object | | Make an iterator that computes the function using arguments from | each of the iterables. Stops when the shortest iterable is exhausted. | | Methods defined here: | | getattribute(self, name, /) | Return getattr(self, name). | | iter(self, /) | Implement iter(self). | | next(self, /) | Implement next(self). | | reduce(...) | Return state information for pickling. | | ---------------------------------------------------------------------- | Static methods defined here: | | new(args, **kwargs) from builtins.type | Create and return a new object. See help(type) for accurate signature.
help>
```
## hex()
Hex() 将整数转换为十六进制。
```python
>>> hex(16)
‘0x10’
>>> hex(False)
‘0x0’
```
## id()
id() 返回对象的标识。
```python
>>> id(orange)
100218832
>>> id({1,2,3})==id({1,3,2})
True
```
## input()
Input() 接受一个标准输入数据，返回为 string 类型。
```python
>>> input("Enter a number")
Enter a number7 ‘7’
```
请注意，输入作为字符串返回。如果我们想把 7 作为整数，我们需要对它应用 int() 函数。
```python
>>> int(input("Enter a number"))
Enter a number7
7
```
## int()
int() 将值转换为整数。
```python
>>> int('7')
7
```
## isinstance()
如果对象的类型与参数二的类型相同则返回 True，否则返回 False。
```python
>>> isinstance(0,str)
False
>>> isinstance(orange,fruit)
True
```
## issubclass()
有两个参数 ，如果第一个类是第二个类的子类，则返回 True。否则，它将返回 False。
```python
>>> issubclass(fruit,fruit)
True
>>> class fruit:`
        pass
>>> class citrus(fruit):
        pass
>>> issubclass(fruit,citrus)
False
```
## iter()
Iter() 返回对象的 python 迭代器。
```python
>>> for i in iter([1,2,3]):
          print(i)
1 2 3
```
## len()
返回对象的长度。
```python
>>> len({1,2,2,3})
3
```
## list()
list() 从一系列值创建一个列表。
```python
>>> list({1,3,2,2})
[1, 2, 3]
```
## locals()
以字典类型返回当前位置的全部局部变量。
```python
>>> locals()
{‘__name__’: ‘__main__’, ‘__doc__’: None, ‘__package__’: None, ‘__loader__’: <class ‘_frozen_importlib.BuiltinImporter’>, ‘__spec__’: None, ‘__annotations__’: {}, ‘__builtins__’: <module ‘builtins’ (built-in)>, ‘fruit’: <class ‘__main__.fruit’>, ‘orange’: <__main__.fruit object at 0x05F937D0>, ‘a’: 2, ‘numbers’: [1, 2, 3], ‘i’: 3, ‘x’: 7, ‘b’: 3, ‘citrus’: <class ‘__main__.citrus’>}
```
## map()
会根据提供的函数对指定序列做映射。
```python
>>> list(map(lambda x:x%2==0,[1,2,3,4,5]))
[False, True, False, True, False]
```
## max()
返回最大值。
```python
>>> max(2,3,4)
4
>>> max([3,5,4])
5
>>> max('hello','Hello')
‘hello’
```
## memoryview()
返回给定参数的内存查看对象(memory view)。
```python
>>> a=bytes(4)
>>> memoryview(a)
<memory at 0x05F9A988>
>>> for i in  memoryview(a): 
        print(i)
```
## min()
min() 返回序列中的最小值。
```python
>>> min(3,5,1)
1
>>> min(True,False)
False
```
## next()
从迭代器返回下一个元素。
```python
>>> myIterator=iter([1,2,3,4,5])
>>> next(myIterator)
1
>>> next(myIterator)
2
>>> next(myIterator)
3
>>> next(myIterator)
4
>>> next(myIterator)
5
```
遍历了所有项目后，再次调用 next() 时，会引发 StopIteration。
```python
>>> next(myIterator)
Traceback (most recent call last):File “<pyshell#392>”, line 1, in <module>
next(myIterator)
StopIteration
```
## object()
Object() 创建一个无特征的对象。
```python
>>> o=object()
>>> type(o)
<class ‘object’>
>>> dir(o)
[‘__class__’, ‘__delattr__’, ‘__dir__’, ‘__doc__’, ‘__eq__’, ‘__format__’, ‘__ge__’, ‘__getattribute__’, ‘__gt__’, ‘__hash__’, ‘__init__’, ‘__init_subclass__’, ‘__le__’, ‘__lt__’, ‘__ne__’, ‘__new__’, ‘__reduce__’, ‘__reduce_ex__’, ‘__repr__’, ‘__setattr__’, ‘__sizeof__’, ‘__str__’, ‘__subclasshook__’]
```
## oct()
oct() 将整数转换为其八进制表示形式。
```python
>>> oct(7)
‘0o7’
>>> oct(8)
‘0o10’
>>> oct(True)
‘0o1’
```
## open()
open() 打开一个文件。
```python
>>> import os
>>> os.chdir('C:\\Users\\lifei\\Desktop')
# Now, we open the file ‘topics.txt’.
>>> f=open('topics.txt')
>>> f
<_io.TextIOWrapper name=’topics.txt’ mode=’r’ encoding=’cp1252′>
>>> type(f)
<class ‘_io.TextIOWrapper’>
```
## ord()
是 chr() 函数或 unichr() 函数的配对函数，它以一个字符（长度为1的字符串）作为参数，返回对应的 ASCII 数值，或者 Unicode 数值
```python
>>> ord('A')
65
>>> ord('9')
57
>>> chr(65)
‘A’
```
## pow()
pow() 有两个参数。比如 x 和 y。它将值返回 x 的 y 次方。
```python
>>> pow(3,4)
81
>>> pow(7,0)
1
>>> pow(7,-1)
0.14285714285714285
>>> pow(7,-2)
0.02040816326530612
```
## print()
用于打印输出，最常见的一个函数。
```python
>>> print("Hello world!")
Hello world!
```
## property()
作用是在新式类中返回属性值。
```python
class C(object):
    def __init__(self):
        self._x = None
    def getx(self):
        return self._x
    def setx(self, value):
        self._x = value
    def delx(self):
        del self._x
    x = property(getx, setx, delx, "I'm the 'x' property.")
```
## range()
可创建一个整数列表，一般用在 for 循环中。
```python
>>> for i in range(7,2,-2):
        print(i)
7 5 3
```
## repr()
将对象转化为供解释器读取的形式。
```python
>>> repr("Hello")
“‘Hello'”
>>> repr(7)
‘7’
>>> repr(False)
‘False’
```
## reversed()
返回一个反转的迭代器。
```python
>>> a=reversed([3,2,1])
>>> a
<list_reverseiterator object at 0x02E1A230>
>>> for i in a:
        print(i)
1 2 3
>>> type(a)
<class ‘list_reverseiterator’>
```
## round()
将浮点数舍入到给定的位数。
```python
>>> round(3.777,2)
3.78
>>> round(3.7,3)
3.7
>>> round(3.7,-1)
0.0
>>> round(377.77,-1)
380.0
```
## set()
创建一个无序不重复元素集合。
```python
>>> set([2,2,3,1])
{1, 2, 3}
```
## setattr()
对应函数 getattr()，用于设置属性值，该属性不一定是存在的。
```python
>>> orange.size
7
>>> orange.size=8
>>> orange.size
8
```
## slice()
slice() 实现切片对象，主要用在切片操作函数里的参数传递。
```python
>>> slice(2,7,2)
slice(2, 7, 2)
>>> 'Python'[slice(1,5,2)]
‘yh’
```
## sorted()
对所有可迭代的对象进行排序操作。
```python
>>> sorted('Python')
[‘P’, ‘h’, ‘n’, ‘o’, ‘t’, ‘y’]
>>> sorted([1,3,2])
[1, 2, 3]
```
## staticmethod()
返回函数的静态方法。
```python
>>> class fruit:
        def sayhi():
            print("Hi")
>>> fruit.sayhi=staticmethod(fruit.sayhi)
>>> fruit.sayhi()
Hi
>>> class fruit:
         @staticmethod
         def sayhi():
            print("Hi")
>>> fruit.sayhi()
Hi
```
## str()
str() 返回一个对象的string格式。
```python
>>> str('Hello')
‘Hello’
>>> str(7)
‘7’
>>> str(8.7)
‘8.7’
>>> str(False)
‘False’
>>> str([1,2,3])
‘[1, 2, 3]’
```
## sum()
将可迭代对象作为参数，并返回所有值的总和。
```python
>>> sum([3,4,5],3)
15
```
## super()
super() 用于调用父类(超类)的一个方法。
```python
>>> class person:
        def __init__(self):
            print("A person")
>>> class student(person):
        def __init__(self):
            super().__init__()
            print("A student")
>>> Avery=student()
A personA student
```
## tuple()
创建一个元组。
```python
(1, 3, 2)
>>> tuple({1:'a',2:'b'})
(1, 2)
```
## type()
返回对象的类型。
```python
>>> type({})
<class ‘dict’>
>>> type(set())
<class ‘set’>
>>> type(())
<class ‘tuple’>
>>> type((1))
<class ‘int’>
>>> type((1,))
<class ‘tuple’>
```
## vars()
vars() 返回对象object的属性和属性值的字典对象。
```python
>>> vars(fruit)
mappingproxy({‘__module__’: ‘__main__’, ‘size’: 7, ‘shape’: ’round’, ‘__dict__’: <attribute ‘__dict__’ of ‘fruit’ objects>, ‘__weakref__’: <attribute ‘__weakref__’ of ‘fruit’ objects>, ‘__doc__’: None})
```
## zip()
zip() 用于将可迭代的对象作为参数，将对象中对应的元素打包成一个个元组，然后返回由这些元组组成的列表。
```python
>>> set(zip([1,2,3],['a','b','c']))
{(1, ‘a’), (3, ‘c’), (2, ‘b’)}
>>> set(zip([1,2],[3,4,5]))
{(1, 3), (2, 4)}
>>> a=zip([1,2,3],['a','b','c'])
>>> x,y,z=a
>>> x
(1, ‘a’)
>>> y
(2, ‘b’)
>>> z
(3, ‘c’)
