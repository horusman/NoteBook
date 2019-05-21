# reload不具有传递性
```
假设模块a.py中import模块b.py，那么如果reload(a)，并不会reload(b)
```
# 实例印证
```
1> 创建两个模块：a.py和b.py，并分别写入一些内容
a.py
>>>import b
>>>b.B()
b.py
>>>def B():
>>>    print("b......")
2> reload一下 a.py
>>>import a
b...
>>>reload(a)
b...
<module 'a' from 'a.pyc'>
3> 修改一下 b.py
>>>def B():
>>>    print("BBBBBB......")
4> 再reload一下a.py（打印结果并未变，即说明reload(a)时没有递归reload(b))
>>>import a
b...
>>>reload(a)
b...
<module 'a' from 'a.pyc'>
```
```
以上论断得到印证！！！
```