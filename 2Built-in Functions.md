## 2 内置函数
* 1 math 
    - 绝对值：abs(-1)
    - 最大最小值：max([1,2,3])、min([1,2,3])
    - 求和：sum(3,5)    //8
    - 序列长度：len('abc')、len([1,2,3])、len((1,2,3))
    - 取模：divmod(5,2) //(2,1)
    - 乘方：pow(2,3,4)  //2**3/4
    - 浮点数：round(1)  //1.0

* 2 function
    - 函数是否可调用：callable(funcname)
    - 类型判断：isinstance(x,list/int)
    - 比较：cmp('hello','hello')
    - 快速生成序列：(x)range([start,] stop[, step])
    - 数据类型：type(name, bases, dict)
    - 输入：input([prompt])
    - 输出：print(*objects, sep=' ', end='\n', file=sys.stdout, flush=False)
    - 查询帮助：help([object])
    - 排序：reversed(seq)
    - 排序：sorted(iterable, *, key=None, reverse=False)
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
    - bin(x) // 二进制
    - hex(x) // 八进制
    - oct(x) // 十进制
    - chr(x) //返回x对应的字符，如chr(65)返回‘A'
    - ord(x) //返回字符对应的ASC码数字编号，如ord('A')返回65

* 4 重要函数
    - filter(function,list)
    - map(function,list[,list])
    - reduce(function,seq[,init])

* 5 非常用函数
    - all(iterable)
    - any(iterable)
    
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

