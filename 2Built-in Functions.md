## 2 内置函数
* 1 math 
    - abs(-1)   //1
    - max([1,2,3] //3
    - min([1,2,3]) //1
    - sum(3,5)  //8
    - len('abc')  //3
    - divmod(5,2) //(2,1)  求商求余       
    - pow(2,3,4) //2**3/4  指数运算
    - round(4.566,1) //4.5 浮点数x的四舍五入

* 2 function 
    - callable(funcname)        // True or Flase        函数是否可调用：
    - isinstance(x,list/int)  //True or Flase    类型判断
    - cmp('hello','hello')    //True or Flase   比较
    - range([start,] stop[, step])// [0,1,2....]  快速生成序列
    - type(name, bases, dict) // int float str dic 判断数据类型
    - input([prompt])  输入
    - print("something") 输出
    - help([object])   查询
    - reversed(seq)     排序
    - sorted(iterable, *, key=None, reverse=False) 排序
    - open(file, mode='r', buffering=-1, encoding=None)  打开文档

* 3 types of Convert
    - int(x)
    - float(x)
    - bool(x)
    - complex(x) //复数
    - str(x)
    - list(x)
    - tuple(x) 
    - dict([object])
    - bin(x) // 二进制
    - hex(x) // 八进制
    - oct(x) // 十进制
    - chr(x) //返回x对应的字符，如chr(65)返回‘A'
    - ord(x) //返回字符对应的ASC码数字编号，如ord('A')返回65

* 4 高阶函数
    - filter(function,list)
    - map(function,list[,list])
    - reduce(function,seq[,init])

* 5 非常用函数
    - all(iterable)
        ```python
        def all():
            """
            返回值 如果iterable的所有元素不为0、''、False或者iterable为空，all(iterable)返回True，否则返回False；
            注意：空元组、空列表返回值为True，这里要特别注意。
            """
            return True   
        ```
    - any(iterable)
        ```python
        def all():
            """
            返回值 如果iterable的所有元素不为0、''、False或者iterable为空，all(iterable)返回True，否则返回False；
            注意：空元组、空列表返回值为True，这里要特别注意。
            """
            return True 
        ``` 

    - dir([object])
    - enumerate(iterable，start = 0 )
    - eval(expression)
    - exec(object [，globals [，locals ] ] )
    - format(value[, format_spec])
    - globals()
    - iter(object[, sentinel])
    - locals()
    - next(iterator[, default]) 
    - repr(object)
    - set([iterable])
    - ascii(object)     
    - 
    - hash(object)
    - memoryview(obj)
    - property(fget=None, fset=None, fdel=None, doc=None)
    - slice(start, stop[, step])
    - super([type[, object-or-type]])
    - vars([object])
    - zip(*iterables)

    - delattr（object，name ）
    - getattr(object, name[, default])
    - setattr(object, name, value)
    - hasattr(object, name)

