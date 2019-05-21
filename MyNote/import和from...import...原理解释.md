# import
```
直接指向源数据本身
```
# from ... import ...
```
是在内存中，新开辟了空间进行存储
相当于是在本地创建了同名的变量指向模块中的同名属性所引用的对象
```
```
注：python是以面向对象为核心思维，所有变量都可以理解为一个对象，都是赋值与引用。
import也不例外，它和其他的变量赋值是一个道理，只不过import赋值了一个和源模块中相同的变量名
```
# 实例印证
```
1> 先创建test.py模块
>>>a = []
>>>b = 1
2> 查看一下每个对象的id
>>>import test
>>>from test import a
>>>id(test)
140544157348872
>>>id(a)
140544157484312
>>>id(test.a)
140544157484312
>>>id(test.b)
8703080
3> 重新加载一下模块
>>>reload(test)
<module 'test' from 'test.pyc'>
4> 再查看一下各个对象的id（发现 id(test.a)发生了变化）
>>>reload(test)
<module 'test' from 'test.pyc'>
>>>id(test)
140544157348872
>>>id(a)
140544157484312
>>>id(test.a)
140544157242576
>>>id(test.b)
8703080
```