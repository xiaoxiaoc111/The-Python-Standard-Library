# 4.内置类型

* ### 4.1. 真值测试

    ###### bool() # False

    以下值被认为是错误的 :

    - `None`
    - `False`
    - 任何数字类型，例如零，`0`，`0.0`，`0j`。
    - 任何空序列，例如`''`，`()`，`[]`。
    - 例如，任何空映射`{}`。
    - 用户定义的类的实例，如果该类定义了一个[`__bool__()`](https://docs.python.org/3.5/reference/datamodel.html#object.__bool__)or [`__len__()`](https://docs.python.org/3.5/reference/datamodel.html#object.__len__)方法，则该方法返回整数零或 [`bool`](https://docs.python.org/3.5/library/functions.html#bool)值`False`。[[1\]](https://docs.python.org/3.5/library/stdtypes.html#id12)

* ### 4.2. 布尔运算 

    - and, or, not

    - | 操作      | 结果                                   | 笔记  |
      | :-------- | :------------------------------------- | :---: |
      | `x or y`  | 如果*x*是假的，那么*y*，否则 *x*       | （1） |
      | `x and y` | 如果*x*是假的，那么*x*，否则 *y*       | （2） |
      | `not x`   | 如果*x*是假的，那么`True`，否则`False` | （3） |

    - #### 笔记：

       1. 这是一个短路运算符，因此如果第一个参数为假，它只会计算第二个参数。
       2. 这是一个短路操作符，所以如果第一个参数为真，它只会计算第二个参数。
       3. `not`具有比非布尔运算符更低的优先级，因此被解释为，并且是语法错误。`not a == b``not (a == b)``a == not b`

* ### 4.3. 比较

   | Operation | 	Meaning                 |
   | -----     | ---------------------------|
   |       |                        |
   | <	       |  严格小于  |
   | <=	       |  小于或等于 |
   | >	       | 严格大于 |
   | >=	       | 大于或等于 |
   | ==	       |  等于                 |
   | !=	       |  不等于            |
   | is	       |  对象身份     |
   | is not    | 否定对象身份 |

* ### 4.4. 数字类型 — int, float, complex

    | 操作	   | Result	                        | 笔记	|
    | ---------------| ---------------------------------| ---------------|
    | x + y	         | *x*和*y*之和	 	 | 	|
    | x - y	         | *x*和*y的*差	| 	|
    | x * y	         | *x*和*y的*乘积	| 	|
    | x / y	         | *x*和*y的*商数	| 	|
    | x // y	     | *x*和 *y的*商数	| （1）	|
    | x % y	         | 剩下的 `x / y`	| （2）	|
    | -x	  | *x*否定	 	           | 	|
    | +x	         | *x*不变	 	         | 	|
    | abs(x)	     | 绝对值或*x的*大小	| 	|
    | int(x)	| *x*转换为整数	| （3）（6）	|
    | float(x)	| *x*转换为浮点	| （4）（6）	|
    | complex(re,im)	| 复数与实部	| （6）	|
    | c.conjugate()	| 复数*c的*共轭	| 	|
    | divmod(x, y)	| (x // y, x % y)	| （2）	|
    | pow(x, y)	| *x*的y次方	| （5）	|
    | x ** y	| *x*的y次方	| （5）	|

    #### 笔记：

    1. 也被称为整数除法。结果值是一个整数，虽然结果的类型不一定是int。结果总是朝着负无穷的方向变化：`1//2`是`0`，`(-1)//2`是 `-1`，`1//(-2)`是`-1`，`(-1)//(-2)`是`0`。
    2. 不适用于复杂的数字。相反，转换为浮动使用[`abs()`](https://docs.python.org/3.5/library/functions.html#abs)。
    3. 从浮点到整数的转换可能在C中舍入或截断; 查看功能[`math.floor()`](https://docs.python.org/3.5/library/math.html#math.floor)和[`math.ceil()`](https://docs.python.org/3.5/library/math.html#math.ceil)定义明确的转换。
    4. 对于非数字（NaN）和正或负无穷，float还接受带有可选前缀“+”或“ - ”的字符串“nan”和“inf”。
    5. Python定义和将会像编程语言一样常见。`pow(0, 0)``0 ** 0``1`
    6. 接受的数字文字包括数字`0`到`9`或任何Unicode当量（与代码点`Nd`属性）。

    - #### 4.4.1. Bitwise Operations on Integer Types

        | 操作   | 结果                  |
        | ------ | --------------------- |
        | x \| y | 按位*或*的*X*和 *ÿ*   |
        | x ^ y  | 按位*异或*的 *X*和*ÿ* |
        | x & y  | 按位*和*的*X*和 *ÿ*   |
        | x << n | *x*左移*n*位          |
        | x >> n | *x*右移*n*位          |
        | ~x     | *x*的位反转           |

* ### 4.5. 迭代器类型

    - iter(object[, sentinel])用来生成迭代器
        ```python
        >>>lst = [1, 2, 3]
        >>>for i in iter(lst):
        >>>     print(i)
        #output 1 2 3
        ```
    - next(iterator[, default]) 返回迭代器的下一个项目
        ```python
        it = iter([1, 2, 3, 4, 5])
        while True:
            try:
            
            # 获得下一个值：
                print(next(it))
            except StopIteration:
                break 
        # 1 2 3 4 5 
        ```

* ### 4.6. 序列类型 — list, tuple, range

    - #### 4.6.1.  常见序列操作

        ​    

        | 操作                 | 结果                                      |        |
        | :------------------- | ----------------------------------------- | ------ |
        | x in s               | `True`如果一个*s*的项等于*x*，否则`False` | (1)    |
        | x not in s           | `False`如果一个*s*的项等于*x*，否则`True` | (1)    |
        | s + t                | *s*和 *t*的连接                           | (6)(7) |
        | s * n or n * s       |                                           | (2)(7) |
        | s[i]                 | 切片                                      | (3)    |
        | s[i:j]               | 切片                                      | (3)(4) |
        | s[i:j:k]             | 切片                                      | (3)(5) |
        | len(s)               | *s的*长度                                 |        |
        | min(s)               | *s的*最小项                               |        |
        | max(s)               | *s的*最大项                               |        |
        | s.index(x[, i[, j]]) | 切片                                      | (8)    |
        | s.count(x)           | 计数                                      |        |

        笔记：

        1. 虽然`in`和操作仅用于简单容纳测试在一般情况下，一些专门的序列（如，和）也将它们用于序列检测：`not in`[`str`](https://docs.python.org/3.5/library/stdtypes.html#str)[`bytes`](https://docs.python.org/3.5/library/functions.html#bytes)[`bytearray`](https://docs.python.org/3.5/library/functions.html#bytearray)
        2. 小于*n的*值`0`被视为`0`（其产生与*s*相同类型的空序列）。请注意，序列中*的*项目不会被复制; 它们被多次引用。这经常困扰着新的Python程序员; 
        3. 如果*i*或*j*是负数，则该索引是相对于序列*s*的末尾： 或被替换。但请注意，依然如此。`len(s) + i``len(s) + j``-0``0` 
        4. 的切片*小号*从*我*到*Ĵ*被定义为物品的具有索引序列 *ķ*使得。如果*我*或*j*大于，请使用 。如果*我*被省略或者使用。如果省略了*j*，或者 使用。如果*我*大于或等于*j*，则切片为空。`i <= k < j``len(s)``len(s)``None``0``None``len(s)`
        5. 步骤*k中*从*i*到*j*的*s*片段被定义为具有这样的索引的项目序列 。换句话说，在指数，，，等等，停车时 *Ĵ*达到（但绝不包括*Ĵ*）。当*k*是正数时，如果它们更大，则 *i*和*j*会减少。当*k*是负数时，如果*i*和*j*更大，则*i*和*j*减小。如果*我*或*j*被省略或`x = i + n*k``0 <= n < (j-i)/k``i``i+k``i+2*k``i+3*k``len(s)``len(s) - 1``None`，它们变成了“终点”值（终点取决于*k*的符号）。请注意，*k*不能为零。如果*k*是`None`，它被视为像`1`。
        6. 串联不可变序列总是会产生一个新对象。这意味着通过重复串联构建序列在总序列长度中将具有二次运行成本。要获得线性运行时成本，您必须切换到以下选项之一：
        7. 某些序列类型（例如[`range`](https://docs.python.org/3.5/library/stdtypes.html#range)）仅支持遵循特定模式的项目序列，因此不支持序列连接或重复。
        8. `index`[`ValueError`](https://docs.python.org/3.5/library/exceptions.html#ValueError)当在*s中*找不到*x*时引发。支持时，index方法的附加参数允许有效地搜索序列的子部分。传递额外的参数大致相当于使用，只是不复制任何数据，并且返回的索引是相对于序列的开始而不是片段的开始。`s[i:j].index(x)`

    - #### 4.6.2. 不可变序列类型

         ```python
            hash()
            set()
            frozenset()
         ```

    - #### 4.6.3 可变序列类型

        | Operation             | Result                                                     |       |
        | --------------------- | ---------------------------------------------------------- | ----- |
        | s[i] = x              | [i] 被替换为 *X*                                           |       |
        | s[i:j] = t            | [i:j] 被替换为 t                                           |       |
        | del s[i:j]            | 与...一样 `s[i:j] = []`                                    | （1） |
        | s[i:j:k] = t          | 元素`s[i:j:k]` 被替换为*t*的元素                           |       |
        | del s[i:j:k]          | `s[i:j:k]`从列表中删除元素                                 |       |
        | s.append(x)           | 将*x*附加到序列的末尾（与之相同 ）`s[len(s):len(s)] =[x]`  |       |
        | s.clear()             | 删除所有项目`s` （与之相同）`del s[:]`                     | （5） |
        | s.copy()              | 创建一个浅的副本`s` （与之相同`s[:]`）                     | （5） |
        | s.extend(t) or s += t | 用*t*的内容扩展*s*（大部分相同 ）`s[len(s):len(s)] = t`    |       |
        | s *= n                | 更新其内容重复*ñ*次                                        | （6） |
        | s.insert(i, x)        | 插入*X*成*小号*由下式给出的指数在*我* （同）`s[i:i] = [x]` |       |
        | s.pop([i])            | 在*i*处检索项目并将其从*s中*移除                           | （2） |
        | s.remove(x)           | 从取出的第一个项目*小号*哪里`s[i] == x`                    | （3） |
        | s.reverse()           | 反转                                                       | （4） |

        #### 笔记：

        1. *t*必须与它正在替换的切片具有相同的长度。

        2. 可选参数*我*默认为`-1`，以便默认情况下最后一项被删除并返回。

        3. `remove`[`ValueError`](https://docs.python.org/3.5/library/exceptions.html#ValueError)当在*s中*找不到*x*时引发。

        4. 该`reverse()`方法在倒转大序列时修改用于空间经济的序列。要提醒用户它是以副作用方式运行的，它不会返回相反的顺序。

        5. `clear()`并且`copy()`包含它们是为了与不支持切片操作的可变容器（例如[`dict`](https://docs.python.org/3.5/library/stdtypes.html#dict)和[`set`](https://docs.python.org/3.5/library/stdtypes.html#set)）的接口一致，

           3.3版新增功能：`clear()`和`copy()`方法。

        6. 值*n*是一个整数或实现的对象 [`__index__()`](https://docs.python.org/3.5/reference/datamodel.html#object.__index__)。*n的*零和负值清除序列。序列中的项目不会被复制; 它们被多次引用，正如在[Common Sequence Operations](https://docs.python.org/3.5/library/stdtypes.html#typesseq-common)下所解释的那样。`s * n`

    - #### 4.6.4.列表

        *class* `list`（[ *iterable* ] ）

        列表可以用几种方式构建：

        - 用一对方括号表示空列表： `[]`
        - 使用方括号，用逗号分隔项目：`[a]`，`[a, b, c]`
        - 使用列表理解： `[x for x in iterable]`
        - 使用类型构造函数：`list()`或`list(iterable)`

        `sort`（***，*key = None*，*reverse = None* ）

        此方法就地对列表进行排序，仅使用`<`项目之间的比较。异常不会被抑制 - 如果任何比较操作失败，整个排序操作将失败（并且列表可能会保留在部分修改状态）。

    - #### 4.6.5 元组

        *class* `tuple`（[ *iterable* ] ）[¶](https://docs.python.org/3.5/library/stdtypes.html#tuple)

        元组可以通过多种方式构建：

        - 使用一对括号来表示空元组： `()`
        - 使用单个元组的尾部逗号：`a,`或`(a,)`
        - 用逗号分隔项目：或`a, b, c``(a, b, c)`
        - 使用[`tuple()`](https://docs.python.org/3.5/library/stdtypes.html#tuple)内置的：`tuple()`或`tuple(iterable)`

        元组实现了所有[常见的](https://docs.python.org/3.5/library/stdtypes.html#typesseq-common)序列操作。 

    - #### 4.6.6 范围

        *class* `range`（*stop* ）

        *类*`range`（*开始*，*停止*[，*步骤*] ）

        范围构造函数的参数必须是整数（内置 [`int`](https://docs.python.org/3.5/library/functions.html#int)或实现`__index__`特殊方法的任何对象）。如果省略*step*参数，则默认为`1`。如果省略*start*参数，则默认为`0`。如果*步*长为零，[`ValueError`](https://docs.python.org/3.5/library/exceptions.html#ValueError)则升起。

* ### 4.7 文本序列类型 - [`str`](https://docs.python.org/3.5/library/stdtypes.html#str)

    * #### 4.7.1。字符串方法

      Python中的文本数据由[`str`](https://docs.python.org/3.5/library/stdtypes.html#str)对象或*字符串*处理。字符串是Unicode代码点的不可变 [序列](https://docs.python.org/3.5/library/stdtypes.html#typesseq)。字符串文字以各种方式书写：

      * 单引号： `'allows embedded "double" quotes'`
      * 双引号：。`"allows embedded 'single' quotes"`
      * 三重引用：，`'''Three single quotes'''``"""Three doublequotes"""`

      字符串实现所有[常见的](https://docs.python.org/3.5/library/stdtypes.html#typesseq-common)序列操作，以及下面描述的其他方法 :



    | 序号 | 方法及描述                                                   |
    | ---- | ------------------------------------------------------------ |
    | 1    | [capitalize()](http://www.runoob.com/python3/python3-string-capitalize.html) 将字符串的第一个字符转换为大写 |
    | 2    | [center(width, fillchar)](http://www.runoob.com/python3/python3-string-center.html) 返回一个指定的宽度 width 居中的字符串，fillchar 为填充的字符，默认为空格。 |
    | 3    | [count(str, beg= 0,end=len(string))](http://www.runoob.com/python3/python3-string-count.html) 返回 str 在 string 里面出现的次数，如果 beg 或者 end 指定则返回指定范围内 str 出现的次数 |
    | 4    | [bytes.decode(encoding="utf-8", errors="strict")](http://www.runoob.com/python3/python3-string-decode.html) Python3 中没有 decode 方法，但我们可以使用 bytes 对象的 decode() 方法来解码给定的 bytes 对象，这个 bytes 对象可以由 str.encode() 来编码返回。 |
    | 5    | [encode(encoding='UTF-8',errors='strict')](http://www.runoob.com/python3/python3-string-encode.html) 以 encoding 指定的编码格式编码字符串，如果出错默认报一个ValueError 的异常，除非 errors 指定的是'ignore'或者'replace' |
    | 6    | [endswith(suffix, beg=0, end=len(string))](http://www.runoob.com/python3/python3-string-endswith.html) 检查字符串是否以 obj 结束，如果beg 或者 end 指定则检查指定的范围内是否以 obj 结束，如果是，返回 True,否则返回 False. |
    | 7    | [expandtabs(tabsize=8)](http://www.runoob.com/python3/python3-string-expandtabs.html) 把字符串 string 中的 tab 符号转为空格，tab 符号默认的空格数是 8 。 |
    | 8    | [find(str, beg=0 end=len(string))](http://www.runoob.com/python3/python3-string-find.html) 检测 str 是否包含在字符串中，如果指定范围 beg 和 end ，则检查是否包含在指定范围内，如果包含返回开始的索引值，否则返回-1 |
    | 9    | [index(str, beg=0, end=len(string))](http://www.runoob.com/python3/python3-string-index.html) 跟find()方法一样，只不过如果str不在字符串中会报一个异常. |
    | 10   | [isalnum()](http://www.runoob.com/python3/python3-string-isalnum.html) 如果字符串至少有一个字符并且所有字符都是字母或数字则返 回 True,否则返回 False |
    | 11   | [isalpha()](http://www.runoob.com/python3/python3-string-isalpha.html) 如果字符串至少有一个字符并且所有字符都是字母则返回 True, 否则返回 False |
    | 12   | [isdigit()](http://www.runoob.com/python3/python3-string-isdigit.html) 如果字符串只包含数字则返回 True 否则返回 False.. |
    | 13   | [islower()](http://www.runoob.com/python3/python3-string-islower.html) 如果字符串中包含至少一个区分大小写的字符，并且所有这些(区分大小写的)字符都是小写，则返回 True，否则返回 False |
    | 14   | [isnumeric()](http://www.runoob.com/python3/python3-string-isnumeric.html) 如果字符串中只包含数字字符，则返回 True，否则返回 False |
    | 15   | [isspace()](http://www.runoob.com/python3/python3-string-isspace.html) 如果字符串中只包含空白，则返回 True，否则返回 False. |
    | 16   | [istitle()](http://www.runoob.com/python3/python3-string-istitle.html) 如果字符串是标题化的(见 title())则返回 True，否则返回 False |
    | 17   | [isupper()](http://www.runoob.com/python3/python3-string-isupper.html) 如果字符串中包含至少一个区分大小写的字符，并且所有这些(区分大小写的)字符都是大写，则返回 True，否则返回 False |
    | 18   | [join(seq)](http://www.runoob.com/python3/python3-string-join.html) 以指定字符串作为分隔符，将 seq 中所有的元素(的字符串表示)合并为一个新的字符串 |
    | 19   | [len(string)](http://www.runoob.com/python3/python3-string-len.html) 返回字符串长度 |
    | 20   | [ljust(width[, fillchar\])](http://www.runoob.com/python3/python3-string-ljust.html) 返回一个原字符串左对齐,并使用 fillchar 填充至长度 width 的新字符串，fillchar 默认为空格。 |
    | 21   | [lower()](http://www.runoob.com/python3/python3-string-lower.html) 转换字符串中所有大写字符为小写. |
    | 22   | [lstrip()](http://www.runoob.com/python3/python3-string-lstrip.html) 截掉字符串左边的空格或指定字符。 |
    | 23   | [maketrans()](http://www.runoob.com/python3/python3-string-maketrans.html) 创建字符映射的转换表，对于接受两个参数的最简单的调用方式，第一个参数是字符串，表示需要转换的字符，第二个参数也是字符串表示转换的目标。 |
    | 24   | [max(str)](http://www.runoob.com/python3/python3-string-max.html) 返回字符串 str 中最大的字母。 |
    | 25   | [min(str)](http://www.runoob.com/python3/python3-string-min.html) 返回字符串 str 中最小的字母。 |
    | 26   | [replace(old, new [, max\])](http://www.runoob.com/python3/python3-string-replace.html) 把 将字符串中的 str1 替换成 str2,如果 max 指定，则替换不超过 max 次。 |
    | 27   | [rfind(str, beg=0,end=len(string))](http://www.runoob.com/python3/python3-string-rfind.html) 类似于 find()函数，不过是从右边开始查找. |
    | 28   | [rindex( str, beg=0, end=len(string))](http://www.runoob.com/python3/python3-string-rindex.html) 类似于 index()，不过是从右边开始. |
    | 29   | [rjust(width,[, fillchar\])](http://www.runoob.com/python3/python3-string-rjust.html) 返回一个原字符串右对齐,并使用fillchar(默认空格）填充至长度 width 的新字符串 |
    | 30   | [rstrip()](http://www.runoob.com/python3/python3-string-rstrip.html) 删除字符串字符串末尾的空格. |
    | 31   | [split(str="", num=string.count(str))](http://www.runoob.com/python3/python3-string-split.html) num=string.count(str)) 以 str 为分隔符截取字符串，如果 num 有指定值，则仅截取 num 个子字符串 |
    | 32   | [splitlines([keepends\])](http://www.runoob.com/python3/python3-string-splitlines.html) 按照行('\r', '\r\n', \n')分隔，返回一个包含各行作为元素的列表，如果参数 keepends 为 False，不包含换行符，如果为 True，则保留换行符。 |
    | 33   | [startswith(str, beg=0,end=len(string))](http://www.runoob.com/python3/python3-string-startswith.html) 检查字符串是否是以 obj 开头，是则返回 True，否则返回 False。如果beg 和 end 指定值，则在指定范围内检查。 |
    | 34   | [strip([chars\])](http://www.runoob.com/python3/python3-string-strip.html) 在字符串上执行 lstrip()和 rstrip() |
    | 35   | [swapcase()](http://www.runoob.com/python3/python3-string-swapcase.html) 将字符串中大写转换为小写，小写转换为大写 |
    | 36   | [title()](http://www.runoob.com/python3/python3-string-title.html) 返回"标题化"的字符串,就是说所有单词都是以大写开始，其余字母均为小写(见 istitle()) |
    | 37   | [translate(table, deletechars="")](http://www.runoob.com/python3/python3-string-translate.html) 根据 str 给出的表(包含 256 个字符)转换 string 的字符, 要过滤掉的字符放到 deletechars 参数中 |
    | 38   | [upper()](http://www.runoob.com/python3/python3-string-upper.html) 转换字符串中的小写字母为大写 |
    | 39   | [zfill (width)](http://www.runoob.com/python3/python3-string-zfill.html) 返回长度为 width 的字符串，原字符串右对齐，前面填充0 |
    | 40   | [isdecimal()](http://www.runoob.com/python3/python3-string-isdecimal.html) 检查字符串是否只包含十进制字符，如果是返回 true，否则返回 false。 |

    * #### 4.7.2。`printf`风格的字符串格式

      字符串对象有一个独特的内置操作：`%`操作符（模）。这也被称为字符串*格式化*或*插值*运算符。鉴于（其中*格式*是字符串），*格式*中的转换规范将替换为零个或多个*值*元素。其效果与在C语言中使用类似。`format %values``%``sprintf()` 

      * 转换说明符包含两个或多个字符，并具有以下组件，它们必须按以下顺序出现：

      1. 该`'%'`字符表示说明符的开始。
      2. 映射键（可选），由括号括起来的字符序列组成（例如`(somename)`）。
      3. 转换标志（可选），影响某些转换类型的结果。
      4. 最小字段宽度（可选）。如果指定为`'*'`（星号），则将从元组的下一个元素的*值中*读取实际宽度，并且要转换的对象位于最小字段宽度和可选精度之后。
      5. 精度（可选），以`'.'`（点）形式给出，然后是精度。如果指定为`'*'`（星号），则实际精度将从元组的下一个元素的*值中*读取，并且要转换的值位于精度之后。
      6. 长度修饰符（可选）。
      7. 转换类型。

      #### 转换类型是：

      | 转变  | 含义                                                         | 笔记  |
      | ----- | ------------------------------------------------------------ | ----- |
      | `'d'` | 带符号的整数小数。                                           |       |
      | `'i'` | 带符号的整数小数。                                           |       |
      | `'o'` | 签署八进制值。                                               | （1） |
      | `'u'` | 已过时的类型 - 与之相同`'d'`。                               | （6） |
      | `'x'` | 签名的十六进制（小写）。                                     | （2） |
      | `'X'` | 签名的十六进制（大写）。                                     | （2） |
      | `'e'` | 浮点指数格式（小写）。                                       | （3） |
      | `'E'` | 浮点指数格式（大写）。                                       | （3） |
      | `'f'` | 浮点十进制格式。                                             | （3） |
      | `'F'` | 浮点十进制格式。                                             | （3） |
      | `'g'` | 浮点格式。如果指数小于-4或小于精度，则使用小写指数格式，否则使用小数格式。 | （4） |
      | `'G'` | 浮点格式。如果指数小于-4或者不小于精度，则使用大写指数格式，否则使用小数格式。 | （4） |
      | `'c'` | 单个字符（接受整数或单个字符串）。                           |       |
      | `'r'` | 字符串（使用任何Python对象转换 [`repr()`](https://docs.python.org/3.5/library/functions.html#repr)）。 | （5） |
      | `'s'` | 字符串（使用任何Python对象转换 [`str()`](https://docs.python.org/3.5/library/stdtypes.html#str)）。 | （5） |
      | `'a'` | 字符串（使用任何Python对象转换 [`ascii()`](https://docs.python.org/3.5/library/functions.html#ascii)）。 | （5） |
      | `'%'` | 没有参数被转换，导致结果中的`'%'` 字符。                     |       |

      #### 笔记：

      1. 替代形式导致`'0o'`在第一个数字之前插入前导八进制说明符（）。

      2. 替代形式会导致在第一个数字之前插入`'0x'`或`'0X'`取决于是否使用了`'x'`或`'X'`格式。

      3. 替代形式会导致结果始终包含小数点，即使没有数字跟着它。

         精度决定小数点后的位数，默认为6。

      4. 替代形式导致结果始终包含小数点，并且尾部零不会像原本那样被删除。

         精度决定小数点前后的有效位数，默认值为6。

      5. 如果精度是`N`，则输出被截断为`N`字符。

      6. 看到 [**PEP 237**](https://www.python.org/dev/peps/pep-0237)。

         

         4.9 set

         4.10 dict

         

         

    

    