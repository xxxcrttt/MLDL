# Python Interview

### Q1. What is Python language? 
**interpreted**: Execures its statements line by line. (Python, Javascript, R, PHP) -- run directly from the source code, not machine-level code before runtime. 
**scripting**: is capable of scripting, but in general-purpose programming. 

### Q2. What are the key features of Python? 
* **interpreted**: does not need to be compiled before running
* **dynamically typed**: dont need to state the type of variables 
* **OOP**: allows the definitions of classes, composition and inheritance
* **functions**: first-class objects, can be assigned to variables, return from and pass into another function. 

### Q3. What is PEP 8?
PEP: Python Enhancement Proposal. Its a set of rules that specify how to format python code for maximum readability. 

### Q4. list vs tuples? 
**list**: mutable -- which can be edited, slower than tuples, []
**tuples**: immutable -- can't be edited, ()

### Q5. namespaces? 
namespace in python refers to the name which is assigned to each object(variables and functions) in Python.     
(Built-in, global, enclosing, local).   
it is used to make sure that names are unique to avoid naming conflicts. 

### Q6. decorators? @ 
Decorators are used to add some design patterns to a function without changing its structure.     
They are generally defined before the function they are enhancing.    
Decorators can be used to check for permissions, modify or track the arguments passed to a methosd, logging the class to a specific method. 

### Q7. dict and list comprehension? 
```Python
# list
x = [i for i in range(5)] 
------
[0,1,2,3,4]
#dict 
x = [i : i+2 for i in range(5)]
------
[0:2,1:3,2:4,3:5,4:6]
```
```Python 
# print the odd numbers btw 0 & 100
x = [a for a in range(0,100) if a%2]
```


**dict**: like hash map    
it stores (key,value) pair, where keys are unique and has O(1) access time.    
Limitation: the keys must be hashable, they cant be changed.


### Q8. common built-in datatypes
**Numbers(integer, floating-point, complex), list, tuple, string, set, dictionary, boolean**

### Q9. slicing
```[start:end:step]```.   
Used to access parts of sequences like lists, tuples and strings. 

### Q10. literals 
literal represents a fixed value for primitive data types. 
**String literal, characrer literal, numeric literal, boolean**    

### Q11. combine dataframe 
```concat()``` is used to concatenate 2 DF. ```pd.concat([dataframe1, dataframe2])```

### Q12. memory manage 
1. **Python private heap space**: All python objects and data structure are located in a private heap. 
2. The allocation of heap space for Python objects is done by Python's memory manager. 
3. Python also has an inbuilt garbafe collector, which recycles all the unused memory. 

### Q13. Python modules 
```os, sys, math, random, datetime, JSON```

### Q14. local variables & global variables. 
1. **Global**: Variables declared outside a function, can be accessed by any function in the program.
2. **Local**: Variables declared inside a function, is presented in the local space. 

### Q15. Case sensitive -- 大小写敏感
YES. Python, JAVA, C++, (SQL不是)

### Q16. type conversion 类型转换
Conversion of one data type into another.   
```int(), float(), ord(), hex(), oct(), tuple(), set(), list(), dict(), str(), complex(real, imag)```

### Q17. identation 缩排
Identation is necessary for Python. 

### Q18. Array vs List
**Array**: only a single data type    
**List**: any data type elements 

### Q19. functions 
a block of code which is executed only when it is called ```def```

### Q20. _init_
a method/constructor to automatically called to allocate memory when a new object/instance of a class is created.    
All classes have the _init_ method. 

### Q. _call_
A callable is an object that can be called, function or an object implementing the _call_ special methods. Any object can be made callable. 

### Q21. Lambda function 
An anonymous function is known as a lambda function.    
This function can have any number of parameters but can have just 1 statement.    
```Python 
a = lambda x, y : x+y
print(a(5,6))
-----
11
```

### Q22. self 
Self is an instance or an object of class. This is explicitly included as the first parameter.   
(Not in Java but only in Python)    
It helps to differentiate between the methods and attributes of a class with local variable. 

### Q23. Break, Continue and Pass
* **Break**: allows loop termination when some condition is met and the control is transferred to the next statement. 
* **Continue**: allows skippinh some part of a loop when some specific condition is met and the control is transferred to the beginning of the loop 
* **Pass**: when need some block of code syntactically, but want to skip its execution. Basically a null operation. 

### Q24. [::-1]
is used to reverse the order of an array or a sequence.    
it reprints a reversed copy of ordered data structures, the original array or list remains unchanged.    
```Python 
arr = [1,2,3,4,5]
arr[::-1]
-----
[5,4,3,2,1]
```

### Q25. randomize the item of a list inplace: 原地打乱
```Python 
random.shuffle()
```

### Q. generator 
A generator is a callable object that acts as an iterable. 

### Q26. iterators
Iterators are objects which can be traversed though or iterated upon. 

### Q27. generate random numbers
```Python 
random.random()
randrange(a,b): [a, b) -- integer 
uniform(a,b): float
normalvariate(mean,sdev): -- normal distribution 
```

### Q28. range & xrange
* **range**: returns a Python list of integers, takes more memory, low spped
* **xrange**: returns an xrange object, a generator object 

### Q29. comments
```# -- sharp ```

### Q30. pickling & unpickling 
```Pickle``` accepts any Python object and converts it into a string representation and dumps it into a file by using ```dump```function.    
```Unpikling``` the process retrieving original Python objects from the stored string representation 

### Q31. Capitalize the first letter 
```capitalize()``` method 

### Q32. convert a string to all lowercase
```lower()``` function 

### Q33. operators
* **is**: returns True when a operands are T 
* **not**: returns the inverse of the boolean value 
* **in**: checks if some element is present in some sequence 

### Q34. help() & dir() 
* **help()**: used to display the documentation string like modules, keywords, attributes
* **dir()**: used to display the defined symbols 

### Q35. dictionary 
The built-in datatypes in Python, defines one-to-one relationship, (key,value) pair. 

### Q36. ternary operators 
It is the operator that is used to show the conditional statement.   
This consists of the T or F values with a statement that has to be evaluated for it. 

### Q37. *args, **kwargs

1. ```*args```: 
when not sure how many arguments are going to be passed to a function. 
or if we want to pass a stored list or tuple of arguments to a function.

2. ```**kwargs```: 
don’t know how many keyword arguments will be passed to a function, or values of a dictionary as keyword arguments. 

### Q38. len()
used to determine the length of a string, a list, an array etc. 

### Q39. split(), sub(), subn() -- re module 
1. **split()**: uses a regex pattern to 'split' a given string into a list.
2. **sub()**: finds all substrings where the regex pattern matches and then replace them with a different string.
3. **subn()**: also returns the new string along with the no. of replacements.

### Q40. negative index [:-1]
[:-1] -- the last integer in the sequence 

### Q41. packages
namespaces containing multiple modules 

### Q42. delete files 
```
import os 
os.remove()
```

### Q43. add/remove value to list 
```
append(), extend(), intert(x,n)
pop(), remove()
```

### Q44. OOP concepts 
Python is an OOP language, any program can be solved in python by creating an object model

### Q45. deep & shallow copy 
1. **shallow copy**: used when a new instance type gets created and it keeps the value that are copied in the new instance 
2. **Deep copy**: used to store the values that are already copied. It doesnt copy the reference pointers to the objects. 

### Q46. Multithreading 多线程
1. Python has a multi-threading package 
2. constructor called Global Interpreter Lock(GIL) -- make sure only one thread can execute

### Q47. compilation & linking 链接器
allow the new extensions to be compiled properly without any error.    
The linking can be done only when it passes the compiled procedure. 

### Q48. libraries 
They are a collection of Python packages
including ```Numpy, Pandas, Matplotlib, Sk-Learn, Tensorflow, Keras```

### Q49. inheritance 继承
Inheritance allows One class to gain all the attributes and methods of another class.   
1. Single -- a derived class acquired the members of a single super class. 
2. multi-level -- a derived class d1 in herited from base class base1, and d2 are inherited from base2. 
3. hierarchical -- from one base class you can inherit any number of child class
4. multiple -- a derived class is inherited from more than one base class. 

### Q50. class
```class``` keyword 

### Q51. monkey patching 猴补丁
only refers to dynamic modifications of a class or module at run-time. 

### Q52. Polymorphism 多态
多态指为不同的 datatype 的 instance 提供统一接口, 或使用一个单一的符号表示多个不同的类型    
Polymorphism means the ability to take multiple forms. 

### Q53. Encapsulation 封装
means binding the code and the data together. Python class is an example of encapsulation 

### Q54. data abstraction 
DA is providing only the required details and hiding the implementation.    
It can be achieved in Python by using iterfaces and abstract classes. 

### Q55. empty class 
empty class means a class that does not have any code defined within its block.   
```Python
class a:
  pass
```
```pass``` keyword does nothing, its a null statement. 

### Q56. object()
It returns a featureless object that is a base for all classes. It does not take any parameters. 

### Q. new & override modifier
1. **new**: used to instruct the compiler to use the new implementation and not the base class function 
2. **Override**: overriding a base class function inside the child class.


# Python Libraries 
### Q57. Flask, Django, Pyramid
1. **Flask**:  is a web microframework, primarily build for a small application with simpler requirements. 
2. **Pyramid**: build for larger applications. It provides flexibility and the developer can chose DB, URL, templating style 
3. **Django**: same as pyramid, it includes an ORM(Object-relation mapping). 

### Q58. Django Architecture

![image](https://user-images.githubusercontent.com/56160038/199251773-d84c314e-f8e8-4ac7-bb73-a0fa02464c7e.png)

The developer provides the Model, the view and the template then just maps it to a URL and Django does the magic to serve it to the user.

### Q59. map function 
map function executes the function given as the 1st argument on all the elements of the iterable given as the 2nd argument. 

### Q60. How to get indices of N maximum values in a NumPy array?
```
print(arr.argsort()[-3:][::-1])
```

### Q61. NumPy & SciPy? 
1. Numpy: Numerical, less linear algebra functions, faster speed
2. SciPy: Scientific, has more linear algebra and algorithms 

**create 1D/2D/3D arrays**:
```Python 
1D = [1,2,3]
2D = [[1,2,3],[2,3,4]]
3D = [[1,2,3],[2,3,4],[3,4,5]]
```

### Q62. Pandas
Pandas is an open-source data manipulation applications,    
including data loading, cleaning / manipulating, preprocessing, modelling and analyzing. 
```
import pandas as pd
df = pd.DataFrame(data, index, columns, dtype)
df.append()
df.concat([df1,df2])
df.join(df2)
```

**indentify with missing value**:
```Python
df.isnull()
df.fullna(0)
```

**delete row/column from DF**:
```Python 
df.drop()
df.drop_duplicates()
```

### Q. XOR in Python 
```
1. (a and not b) or (not a and b)
2. bool(a) != bool(b)
3. bool(a)^bool(b)
4. from operator import xor
   xor(bool(a), bool(b))
```





