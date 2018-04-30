## 2 内置函数
* 1 math 
    - 绝对值：abs(-1)   //1
    - 最大值：max([1,2,3] //3
    - 最小值：min([1,2,3]) //1
    - 求和：sum(3,5)  //8
    - 求长度：len('abc')  //3
    - 求商求余：divmod(5,2) //(2,1)         
    - 乘方指数：pow(2,3,4) //2**3/4  
    - 浮点数精度：round(4.566,1) //4.5 

* 2 function 
    - 判定函数调用：callable(funcname)  // True or Flase        
    - 判断数据类型：isinstance(x,list/int)  //True or Flase   
    - 生成有序序列：range([start,] stop[, step])// [0,1,2....]  
    - 判断数据类型：type(name, bases, dict) // int float str dic 
    - 输入函数：input([prompt])  
    - 输出函数：print("something") 
    - 查询函数：help([object])   
    - 反序函数：reversed(seq)   //函数用于反向列表中元素
    - 排序函数：sorted(iterable, *, key=None, reverse=False) 
    - 打开文档：open(file, mode='r', buffering=-1, encoding=None) 

* 3 types of Convert
    - int(x)
    - float(x)
    - bool(x)
    - complex(x) //复数
    - str(x)
    - list(x)
    - tuple(x) 
    - dict([object])
    - 二进制转换：bin(x) 
    - 八进制转换：hex(x) 
    - 十进制转换：oct(x) 
    - chr(x) //返回x对应的字符，如chr(65)返回‘A'
    - ord(x) //返回字符对应的ASC码数字编号，如ord('A')返回65

* 4 高阶函数
    - 过滤序列函数：filter(function, iterable) 
        ```python
            def is_odd(n):
                """
                ilter() 函数用于过滤序列，过滤掉不符合条件的元素，返回由符合条件元素组成的新列表。
                该接收两个参数，第一个为函数，第二个为序列，序列的每个元素作为参数传递给函数进行判，然后返回 True 或 False，最后将返回 True 的元素放到新列表中。
                """
                return n % 2 == 1
            newlist = filter(is_odd, [1, 2, 3, 4, 5, 6, 7, 8, 9, 10])
            print(newlist) #output [1, 3, 5, 7, 9]  
        ```
    - 映射函数：map(function, iterable, ...)
        ```python
            def square(n):
                """
                map() 会根据提供的函数对指定序列做映射。第一个参数 function 以参数序列中的每一个元素调用 function 函数，返回包含每次 function 函数返回值的新列表。
                """
                return x**2
            map(square, [1, 2, 3, 4, 5])
            #output [1, 4, 9, 16, 25]  
            map(lambda x: x ** 2, [1, 2, 3, 4, 5])
            #output [1, 4, 9, 16, 25]  
            map(lambda x, y: x + y, [1, 3, 5, 7, 9], [2, 4, 6, 8, 10])
            #output[3, 7, 11, 15, 19]
        ```
    - reduce(function,seq[,init])
        ```python
            def add(x, y):
                """
                reduce() 函数会对参数序列中元素进行累积。函数将一个数据集合（链表，元组等）中的所有数据进行下列操作：用传给reduce中的函数 function（有两个参数）先对集合中的第 1、2 个元素进行操作，得到的结果再与第三个数据用 function 函数运算，最后得到一个结果。
                """
                return x+y
            reduce(add, [1, 2, 3, 4, 5])
            #output 15  
            reduce(lambda x, y: x+y, [1,2,3,4,5]) 
            #output 15  

        ```

* 5 非常用函数
    - all(iterable)
        ```python
        def all():
            """
            返回值 如果iterable的所有元素不为0、''、False或者iterable为空，all(iterable)返回True，否则返回False；
            注意：空元组、空列表返回值为True，这里要特别注意。
            """
            for element in iterable:
            if not element:
                return False
            return True  
        ```
    - any(iterable)
        ```python
        def all():
            """
            返回值 如果iterable的所有元素不为0、''、False或者iterable为空，all(iterable)返回True，否则返回False；
            注意：空元组、空列表返回值为True，这里要特别注意。
            """
            def any(iterable):
                for element in iterable:
                    if element:
                        return True
            return False
        any(['a', 'b', '', 'd'])   #True 列表list，存在一个为空的元素
        any([0, '', False])        #False 列表list,元素全为0,'',false
        ``` 
    - dir([object])
    - enumerate(iterable，start = 0 )
        ```python
            seasons = ['Spring', 'Summer', 'Fall', 'Winter']
            list(enumerate(seasons))
            #output[(0, 'Spring'), (1, 'Summer'), (2, 'Fall'), (3, 'Winter')]
        ```
    - eval(expression)
    - exec(object [，globals [，locals ] ] )
    - format(value[, format_spec])
        ```python
        >>>"{} {}".format("hello", "world")    # 不设置指定位置，按默认顺序
            'hello world'
        >>> "{0} {1}".format("hello", "world")  # 设置指定位置
            'hello world'
        >>> "{1} {0} {1}".format("hello", "world")  # 设置指定位置
            'world hello world'
        >>> print("{:.2f}".format(3.1415926));
            3.14
        ```
    - iter(object[, sentinel])用来生成迭代器
        ```python
            >>>lst = [1, 2, 3]
            >>>for i in iter(lst):
            >>>     print(i)
            #output 1 2 3
    - next(iterator[, default]) 返回迭代器的下一个项目
        ```python
        it = iter([1, 2, 3, 4, 5])
        while True:
            try:
            # 获得下一个值:
                print(next(it))
            except StopIteration:
                break 
        # 1 2 3 4 5
        ```
    - set([iterable])
        ```python
        #set()创建一个无序不重复元素集，可进行关系测试，删除重复数据，还可以计算交集、差集、并集等
        >>>x = set('runoob')
        >>> y = set('google')
        >>> x, y
            (set(['b', 'r', 'u', 'o', 'n']), set(['e', 'o', 'g', 'l']))   # 重复的被删除
        >>> x & y         # 交集
            set(['o'])
        >>> x | y         # 并集
            set(['b', 'e', 'g', 'l', 'o', 'n', 'r', 'u'])
        >>> x - y         # 差集
            set(['r', 'b', 'u', 'n'])
        ```
    - globals() 以字典类型返回当前位置的全部全局变量 
    - locals() 以字典类型返回当前位置的全部局部变量
    - vars([object])返回对象object的属性和属性值的字典对象类似 locals()
    
    - id([object])用于获取对象的内存地址
    - repr(object)将对象转化为供解释器读取的形式
   
    - ascii(object)     
    - hash(object)返回对象的哈希值
    - memoryview(obj)返回给定参数的内存查看对象
    - class property([fget[, fset[, fdel[, doc]]]])在新式类中返回属性值
    - reload()用于重新载入之前载入的模块
    - slice(start, stop[, step])实现切片对象，主要用在切片操作函数里的参数传递。
    - super([type[, object-or-type]])
    - staticmethod()  返回函数的静态方法
    - zip(*iterables)对象中对应的元素打包成一个个元组，然后返回由这些元组组成的列表。

    - delattr（object，name ）用于删除属性值，该属性必须存在
    - getattr(object, name[, default])用于设置属性值，该属性必须存在
    - setattr(object, name, value)对应函数 getatt()，用于设置属性值，该属性必须存在
    - hasattr(object, name) 用于判断对象是否包含对应的属性


