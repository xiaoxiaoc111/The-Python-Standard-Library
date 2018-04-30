## 4. Built-in Types

* 4.1. Truth Value Testing
    bool() # False
    - constants defined to be false: None and False.
    - zero of any numeric type: 0, 0.0, 0j, Decimal(0), Fraction(0, 1)
    - empty sequences and collections: '', (), [], {}, set(), range(0)    

* 4.2. Boolean Operations 
    - and, or, not

* 4.3. Comparisons

   | Operation | 	Meaning                 | 
   | -----     | ---------------------------|
   | :---      | :---                       |  
   | <	       |  strictly less than        |
   | <=	       |  less than or equal        |
   | >	       |  strictly greater than     |
   | >=	       |  greater than or equal     |
   | ==	       |  equal                     |
   | !=	       |  not equal                 |
   | is	       |  object identity           |
   | is not    |  negated object identity   |

* 4.4. Numeric Types — int, float, complex

    | Operation	     | Result	                        | 
    | ---------------| ---------------------------------|
    | x + y	         | sum of x and y	 	            | 
    | x - y	         | difference of x and y	 	    | 
    | x * y	         | product of x and y	 	        | 
    | x / y	         | quotient of x and y	 	        |  
    | x // y	     | floored quotient of x and y	    |  
    | x % y	         | remainder of x / y	            |  
    | -x	         | x negated	 	                |  
    | +x	         | x unchanged	 	                | 
    | abs(x)	     | absolute value or magnitude of x	|  	
    | int(x)	     | x converted to integer	        | 
    | float(x)	     | x converted to floating point	| 
    | complex(re, im)|  a complex number withrealpart re| 
    | c.conjugate()	 | conjugate of the complex number c| 	 	 
    | divmod(x, y)	 | the pair (x // y, x % y)	        | 
    | pow(x, y)	     | x to the power y	                | 
    | x ** y	     | x to the power y                 | 

    - 4.4.1. Bitwise Operations on Integer Types

        | Operation	| Result	                        | 
        | x | y	    | bitwise or of x and y	            | 
        | x ^ y	    | bitwise exclusive or of x and y	|  
        | x & y	    | bitwise and of x and y	        |  
        | x << n	| x shifted left by n bits	        | 
        | x >> n	| x shifted right by n bits	        | 
        | ~x	    | the bits of x inverted	        | 

* 4.5. Iterator Types
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
            # 获得下一个值:
                print(next(it))
            except StopIteration:
                break 
        # 1 2 3 4 5 

* 4.6. Sequence Types — list, tuple, range
    - 4.6.1. Common Sequence Operations 常见序列操作
        | Operation	            | Result	                                            | 
        | x in s	            | True if an item of s is equal to x, else False	    | 
        | x not in s            | 	False if an item of s is equal to x, else True	    | 
        | s + t	                |   the concatenation of s and t	                    | 
        | s * n or n * s        | 	equivalent to adding s to itself n times	        | 
        | s[i]	                | ith item of s, origin 0	                            | 
        | s[i:j]	            | slice of s from i to j	                            | 
        | s[i:j:k]	            | slice of s from i to j with step k	                | 
        | len(s)	            | length of s	                                        | 
        | min(s)	            | smallest item of s	                                | 
        | max(s)	            | largest item of s	                                    | 
        | s.index(x[, i[, j]])  | 	index of the first occurrence of x in s (at or after index i and before index j)                                                           | 	
        | s.count(x)	        | total number of occurrences of x in s                 | 
    - 4.6.2. Immutable Sequence Types 不可变序列类型
         ```python
            hash()
            set()
            frozenset()
         ```
    - 4.6.3  Mutable Sequence Types   可变序列类型
        | Operation	    | Result	                     | Notes|
        | s[i] = x	    | item i of s is replaced by x	 ||
        | s[i:j] = t    | slice of s from i to j is replaced by the contents of the iterable ||
        | del s[i:j]    | same as s[i:j] = []	         ||
        | s[i:j:k] = t	| the elements of s[i:j:k] are replaced by those of t|	(1)|
        | del s[i:j:k]	| removes the elements of s[i:j:k] from the list	| |
        | s.append(x)	| appends x to the end of the sequence (same as s[len(s):len(s)] = [x])||	 
        | s.clear()	removes all items from s (same as del s[:])|	(5)|
        | s.copy()	creates a shallow copy of s (same as s[:])|	(5)|
        | s.extend(t) or s += t	extends s with the contents of t (for the most part the same as s[len(s):len(s)] = t)	| |
        | s *= n	updates s with its contents repeated n times	|(6)|
        | s.insert(i, x)	inserts x into s at the index given by i (same as s[i:i] = [x])	| |
        | s.pop([i])	retrieves the item at i and also removes it from s	|(2)|
        | s.remove(x)	remove the first item from s where s[i] == x	|(3)|
        | s.reverse()	reverses the items of s in place|	(4)|
