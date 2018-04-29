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
    | :---           | :---                             |  
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