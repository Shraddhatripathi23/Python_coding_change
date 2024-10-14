# Python Coding Interview Questions


<!-- Content-->
##  Balanced paraenthsis

```python

def paraCheck( seq ):  
   while True:  
       if '()' in seq :  
           seq = seq.replace ( '()' , '' )  
       elif '{}' in seq :  
           seq = seq.replace ( '{}' , '' )  
       elif '[]' in seq :  
           seq = seq.replace ( '[]' , '' )  
       else :  
           return not seq  
  
seq = '{[()]}'  
print({paraCheck(seq)})  
seq1 = '{[()]}{]{}}'  
print( {paraCheck (seq1)})  

```

##  Inhrtitance 
#Single Inheritance 

```python
#  Single Inheritance
class A:
    def displayinfoA(self):
        print("-- Welcome to parents class --")
        
class B(A): 
    def displayinfoB(self):
        print(" --Welcome to child class  -- ")
        
obj = B()
obj.displayinfoA()
obj.displayinfoB() 

> Output - 
-- Welcome to parents class --
 --Welcome to child class  -- 


```


## Multipal Inheritance 

```python


class A:
    def displayinfoA(self):
        print("-- Welcome to parents class --")
        
class B: 
    def displayinfoB(self):
        print(" --Welcome to child  B class  -- ")
        
class C(A,B): 
    def displayinfoC(self):
        print(" --Welcome to child  C class  -- ")
        
obj = C()
obj.displayinfoA()
obj.displayinfoB() 
obj.displayinfoC()

> Output - 
-- Welcome to parents class --
 --Welcome to child  B class  -- 
 --Welcome to child  C class  -- 
```

## Multilevel  Inheritance 

```python


class A:
    def displayinfoA(self):
        print("-- Welcome to parents class --")
        
class B(A): 
    def displayinfoB(self):
        print(" --Welcome to child  B class  -- ")
        
class C(B): 
    def displayinfoC(self):
        print(" --Welcome to child  C class  -- ")
        
obj = C()
obj.displayinfoA()
obj.displayinfoB() 
obj.displayinfoC()


> Output - 
-- Welcome to parents class --
 --Welcome to child  B class  -- 
 --Welcome to child  C class  -- 
```

## Overloading In Python
```python
class overloading :
    def displayinfo(self ,name=''):
        print("Welcome to overlaoding program" + " "   +name)
    
obj = overloading()
obj.displayinfo()
obj.displayinfo('shraddha')

> Output -
Welcome to overlaoding program 
Welcome to overlaoding program shraddha

```


## Overriding In python 

```python

class overriding:
    def find_area(self ,a= None ,b= None):
        if a!=None and b!=None :
            print("Area for reactangle is = ",(a*b))
        elif a!=None:
            print("Area of square is = ",(a*a))
        else:
            print("Not find anything ")
            
obj = overriding()
obj.find_area(10)
obj.find_area(10,20)
obj.find_area()

> Output - 
Area of square is =  100
Area for reactangle is =  200
Not find anything 
```

## Encapsulation In python 

```python
class finance :
    def __init__(self):
        self.revenue = 1000  # data
        self.employee =123

f1= finance()
print(f1.__dict__)

class HR:
    def __init__(self):
        self.panel = 1000 # able to update finance data, which is a problem so for this problem we are using Encasulation
        f1.revenue = 2
        
h1 = HR()
print(f1.__dict__)


> Output - 
{'revenue': 1000, 'employee': 123}
{'revenue': 2, 'employee': 123}
```

How to achieve this 

``` python
class finance :
    def __init__(self):
        self.__revenue = 1000  # data
        self.__employee =123

    def display(self):
        print(  {self.__revenue} and  {self.__employee})
f1= finance()
f1.display()
print(f1.__dict__)  --> can use access  private data 

> Output -
{123}

#Name Mangling in python
The purpose of name mangling is to avoid unintentional access of private class members. Explanation: Name mangling prevents unintentional access by private members of a class, while still allowing access when needed. Unless the variable is accessed with its mangled name, it will not be found.

It will store private variables as _classname_variable_name, so Python cannot fully define private data using Encapsulation’s  method also .


```

# if we define private variable in another class and try to update value so it will create that class variable
```python

class finance :
    def __init__(self):
        self.__revenue = 1000  # data
        self.__employee =123

    def display(self):
        print(  {self.__revenue} and  {self.__employee})
f1= finance()
f1.display()
print(f1.__dict__)

class HR:
    def __init__(self):
        self.panel = 1000 # able to update finance data which coz problem so for this problem we are using Encasulation
        f1.__revenue = 2
        
h1 = HR()
print(f1.__dict__)

> Output-
{123}
{'_finance__revenue': 1000, '_finance__employee': 123}
{'_finance__revenue': 1000, '_finance__employee': 123, '_HR__revenue': 2}

```
## Abstraction In Python

``` python
from abc import ABC, abstractmethod 

class Car(ABC):
    def milage(self):
        pass 
    
    def color(self):
        print("white")
        
class marutui_suzuki(Car):
    def milage(self):
        print(" marutui_suzuki milage is 80 kmph")
        
class TATA(Car):
    def milage(self):
        print("TATA milage is 100 kmph")

class Bugatti(Car):
    def milage(self):
        print("Bugatti milage is 200 kmph")
   
m1 = marutui_suzuki()
t1 = TATA()
b1 = Bugatti()

m1.milage()
m1.color()
t1.milage()
b1.milage()
b1.color()

>Output -
marutui_suzuki milage is 80 kmph
white
TATA milage is 100 kmph
Bugatti milage is 200 kmph
white

```

##  Second higest element in List without build in function

```python
list1 = [10,20,30,50 ,89,90]
largest = list1[0]
second_highest = list1[0]

for i in range (len(list1)):
    if list1[i] > largest:
        largest = list1[i]
print(largest)

for i in range (len(list1)):
    if list1[i]> second_highest and list1[i]!=largest:
        second_highest = list1[i]
print(second_highest)

> 90
> 89
```
## Decorator In python

```python

def decorartor(addition):
    def inner():
        result = addition()
        num3 = int (input ("enter thired no to check decorartor functionality in python"))
        result = result + num3
        return result
    return inner
    
@decorartor

def addition():
    num1 = int(input(" enter first no "))
    num2 = int(input (" enter second no"))
    result = num1 + num2
    return result
    
print(" addition is ", addition())

```
## Python program to reverse a number

```python

n = int (input ("enter any no : - "))
print("Original no is ",n)
revsere = 0
while n!=0:
    revsere = revsere *10 + n%10
    n = (n//10)
print("After revsere no ", revsere)

enter any no : - 12345
Original no is  12345
After revsere no  54321

```
## Armstrong number program in python 
```python

n = int (input ("enter any no : - "))
print("Original no is ",n)
sum1 = 0 
tmp = n
count = len(str(n))
while tmp !=0:
    digit = tmp % 10
    sum1 += digit ** count
    tmp = tmp //10
if sum1 == n :
    print("Yes Armstrong No")
else:
    print("Not Armstrong”)

enter any no : - 153
Original no is  153
Yes Armstrong No

```
## Prime number program in python 
```python
#Prime no
n = int(input("please give a number : "))
tmp = 0
for i in range(2,n//2):
    if  n%i == 0:
        tmp =  1
        break
if tmp == 1:
    print("Not prime no")
else:
    print("prime no")

please give a number : 11
prime no
```

##  Common leters between two strings

```python
str1 = input ("Enter a string1 : - ")
str2 = input("ENTER 2nd string2:- ")

s1 = set(str1)
s2 = set(str2)

output = s1 & s2
print("Common letter is :- ",output)

> Output - 
Enter a string1 : - shraddha
ENter 2nd string2:- tripathi
Common letter is :-  {'a', 'h', 'r'}


```

##  OCCURANCE OF EACH LETTERS USING dictionary 

```python

str1 = input ("Enter a string1 : - ")
d = {}
for i in str1:
    if i in d:
        d[i] = d[i] + 1
        
    else:
        d[i] = 1 
print(d)

> Output - 
Enter a string1 : - shraddha
{'s': 1, 'h': 2, 'r': 1, 'a': 2, 'd': 2}


```

##  Generator with fibonacci

```python
def fibonacci():
    x, y = 0, 1
    while True:
        yield x
        x, y = y, x + y

# Accept input from the user
n = int(input("Input the number of Fibonacci numbers you want to generate? "))

print("Number of first ",n,"Fibonacci numbers:")
fib = fibonacci()
for _ in range(n):
    print(next(fib),end=" ")

> Output - 
Input the number of Fibonacci numbers you want to generate? 11
Number of first  11 Fibonacci numbers:
0 1 1 2 3 5 8 13 21 34 55 



```

##  Remove any specific letter to your string 

```python
String_input = (input("Input the Input string "))
output = (input("Input the letter which you want to remove in string "))
print(String_input.replace(output, ""))

> Output - 
Input the Input string shraddha
Input the letter which you want to remove in string a
shrddh



```

##  Class exp

```python

class Employee:
    def __init__(self, id, name, basic, da):
        self.id = id
        self.name = name
        self.basic = basic
        self.da = da
    
    def getsalary(self):
        return self.basic + self.da

# Creating an instance of the Employee class
emp = Employee(1, "John Doe", 5000, 2000)

# Calling the getsalary() method
salary = emp.getsalary()
print("Total Salary:", salary)

> Output - 
Total Salary: 7000


```

## 2nd largest element without build-in 
```python
list1 = [100,50 ,10,20,30,50 ,89,90,100]
largest = list1[0]
second_highest = list1[1]
n=len(list1)

for i in range (len(list1)):
    if list1[i] > largest:
        largest = list1[i]
print(largest)

for i in range (2,n):
    if list1[i]> second_highest and list1[i]!=largest:
        second_highest = list1[i]
print(second_highest)

> Output - 
100
90


```

##  Combine word alternate 

```python
def combine_words(word1, word2):
    i = j = 0
    result = ""
    while i < len(word1) and j < len(word2):
        result += word1[i] + word2[j]
        i += 1
        j += 1
    return result
word1 = "abc"
word2 = "def"
result = combine_words(word1, word2)
print(result)  

> Output - 
adbecf


```
##  Occurance of no in given list

```python
def occurance(l1,num):
    count =0
    for i in l1:
        if i==num:
            count = count +1
    return count
l1 = [12,2,2,1,2,3]
print("User list is : - ",l1)
print("occurance of given no is in linst :-",occurance(l1,2))

> Output - 
User list is : -  [12, 2, 2, 1, 2, 3]
occurance of given no is in linst :- 3


```
##  Sum of given list without build-in

```python
def sum_of_no(l1):
    count =0
    for i in l1:
        count = i+count
    return count
    #print(count)
l1 = [2,3,4,5]
print(l1)
print("Addition is:",sum_of_no(l1))

> Output - 
[2, 3, 4, 5]
Addition is: 14


```
##  Diagonal addtion of given matrix

```python
list1 = [[1,2,3], [4,5,6],[7,8,9]]
s1 = print(list1[0][0])
s2 = print(list1[1][1])
s3 = print(list1[2][2])


output1 = list1[0][0] + list1[1][1] + list1[2][2]
print("Output is :- " , output1)

> Output - 
1
5
9
Output is :-  15


```

```
##  Inhrtitance 

```python
console.log("1" + 1);
console.log("A" - 1);
console.log(2 + "-2" + "2");
console.log("Hello" - "World" + 78);
console.log("Hello"+ "78");

> Output - 

11
NaN
2-22
NaN
Hello78

```

```
## Python program to find the union and intersection of two arrays

```python

a=list(map(int,input('Enter elements of first list:').split()))
b=list(map(int,input('Enter elements of second list:').split()))

A=list(set(a)|set(b))
B=list(set(a)&set(b))

print('Union of the arrays:',A)
print('intersection of the arrays:',B)

> Output -
Enter elements of first list:1 3 4 5 6 7
Enter elements of second list:3 8 9 
Union of the arrays: [1, 3, 4, 5, 6, 7, 8, 9]
intersection of the arrays: [3]



```
```
##  Output:

```python
11 = [10, 20, 30,40]
12 = [10, 20, 30,40]
print( 11 is 12) #False
print( 11 == 12) #True
13 = 11
print(11 is 13) #True
print 11 == 13) #True

> Output - 



```
```
##  Inhrtitance 

```python


> Output - 
# Python Coding Interview Questions


<!-- Content-->
##  Balanced paraenthsis

```python

def paraCheck( seq ):  
   while True:  
       if '()' in seq :  
           seq = seq.replace ( '()' , '' )  
       elif '{}' in seq :  
           seq = seq.replace ( '{}' , '' )  
       elif '[]' in seq :  
           seq = seq.replace ( '[]' , '' )  
       else :  
           return not seq  
  
seq = '{[()]}'  
print({paraCheck(seq)})  
seq1 = '{[()]}{]{}}'  
print( {paraCheck (seq1)})  

```


```
```
##  Inhrtitance 

```python


> Output - 



```
```
##  Inhrtitance 

```python

Q1. What is the difference between is operator and == operator in python?
In general, is operator meant for reference comparison or Address comparison. ie
if two references are pointing to the same object, then only is operator returns
True.
== operator meant for content comparison. i.e eventhough objects are different, if
the content is the same then == operator returns True.

11 = [10, 20, 30,40]
12 = [10, 20, 30,40]
print( 11 is 12) #False
print( 11 == 12) #True
13 = 11
print(11 is 13) #True
print 11 == 13) #True


Q2. Explain about Ternary Operator or Conditional Operator?
x = firstValue if condition else secondValue
if condition is True then firstValue will be considered,otherwise second value
will be considered.
eg-1:
eg-1:

# Find Max of 2 given numbers
a = int (input ('Enter First Value:'))
b = int (input ('Enter Second Value:'))
max = a if a>b else b
print (f'Maximum Value: '‚max)


D: \durgaclasses›py test.py
Enter First Value:10
Enter Second Value: 20
Maximum Value: 20

===============================

Q3. What are various inbuilt data types available in python?
1. int
2. float
3. complex
4. str(string)
5. bool
6. list
7. tuple
8. set
9. dict
10. frozenset
11. bytes
12. bytearray
13. range
etc

=================================

Q4. Explain mutability and immutability with an example?
mutable means changeable where as immutable means non-changeable.
Once we creates an object, if we are allowed to change its content that object is
said to be mutable object.
eg:
1 = [10,20, 30, 40]
print ('Before modification:',1)
1[21 = 7777
print ('After Modification:', 1)

Once we creates an object, if we are not allowed to change its content then that
object is said to be immutable.
eg: tuple object is immutable.


s = 'abcdef'
S[0]=
'×' #TypeError:
#TypeError; 'str' object does not support item assignment

===============================
egl: tuple object is immutable.
t = (10, 20,30,40)
t [2] = 7777 # TypeError: 'tuple' object does not support item assignment
eg2: string object is immutable
s = 'abcdef'
[0] = '×' #TypeError: 'str' object does not support item assignment

==============================
Q5. In Python which objects are mutable and which objects are immutable?
1. int ---›immutable
2. float ---›immutable
3. complex ---›immutable
4. str(string) ---›immutable
5. bool---›immutable
6. list- - -›mutable
7. tuple- - -›immutable
8. set ---›mutable
9. dict ---›mutable
10. frozenset ---›immutable
11. bytes ---›immutable
12. bytearray ---›mutable
13. range---›immutable 

========================================================

6. Explain the differences between list and tuple?
1. List is a group of comma separated values within square brackets and square
brackets are mandatory.
eg: 1 = [10, 20,30,40]

1. Tuple is a group of comma separated values within parenthesis and parenthesis
are optional.
eg: t= (10, 20, 30,40)
t= 10, 20, 30, 40

2. List objects are mutable. ie once we creates List object, we can change its
content.
1[0] = 7777

2. Tuple objects are immutable. ie once we creates Tuple object, we are not
allowed to change its content.
t [0] = 7777 #TypeError

3. List objects require more memory.
3. Tuple objects require less memory.


import sys

l1 = [1, 2, 3, 4, 5]
print('The Size of List:', sys.getsizeof(l1))

l2 = (1, 2, 3, 4, 5)
print('The Size of List:', sys.getsizeof(l2))

import sys
1 = [10,20, 30,40,50,60, 70,80,90, 100]
t = (10,20,30,40,50, 60, 70,80,90, 100)
print('The Size of List:'‚sys.getsizeof(1))
print('The Size of Tuple:',sys.getsizeof (t))
o/p:
The Size of List: 136
The Size of Tuple: 120

4. List objects won't be reusable.
4. Tuple objects are reusable.
11 = [10, 20, 30,40, 50, 60, 70, 80, 90, 100) Pailup fiorp
12 = [10, 20, 30, 40, 50, 60, 70,80,90, 100
t1 = (10, 20, 30,40, 50, 60, 70, 80, 90, 100
t2 = (10,20, 30,40, 50, 60, 70, 80, 90, 100
print(id(11))
print(id(12))
print(id(t1))
36
print(id(t2))

5. Performance of List is Low, ie operations on List object require more time.
5. Performance of Tuple is High, ie operations on Tuple object require less time.

6. Comprehension concept is applicable for List
6. Comprehension concept is not applicable for Tuple

7. List objects are unhashable type and hence we cannot store in set and in dict
as keys.
s = {10,20,30, [40,50]} #TypeError: unhashable type: 'list'
s = { [10,20]:'durga'} #TypeError: unhashable type: 'list'
7. Tuple objects are hashable type and hence we can store in set and in dict as
keys.
s = {10,20, 30, (40,50)} #Valid
s = { (10, 20) : ' durga*; #valid

8. If the content is not fixed and keep on changing then it is recommended to go
for list objects.
eg: To store youtube comments
8. If the content is fixed and never changes then we should go for tuple objects.
eg: Allowed input values for vendor machine.

Q. What is the difference between Set and FrozenSet?
All properties of set and frozenset are same except the following difference:
'Set is mutable where as frozenset is immutable'
eg:
S= (10,20, 30,403
Is.add (50)
print (s) #{40, 10, 50, 20, 30}
We can add new elements to the set as it is mutable

eI
S={10,20,30,40}
fs = frozensets)
fs.add(50) #AttributeError: 'frozenset' object has no attribute 'add'
print(fs)
As FrozenSet is immutable, add,remove such type of terminology is not applicable.


1. List is a group of comma separated individual objects within square brackets.
eg: 1= [10, 20,30,40]
1. Dict is a group of comma separated key-value pairs within curly braces.
eg: d = {'A': 'Apple', 'B': 'Banana'.
, 'C': 'Cat'}


2. In List, Insertion Order is preserved
2. In Dict, All key-value pairs will be stored based on hashcode of keys and hence
insertion Order is not preserved. But from 3.7 version onwards, the dict
functionality internally replaced with OrderedDict functionality. Hence from 3.7
version onwards, in the case of normal dict also insertion order can be
guaranteed.

3. In List, Duplicate objects are allowed.
3. In Dict, Duplicate keys are not allowed, but values can be duplicated. If we
are trying to add an entry (key-value pair) with duplicate key then old value will
be replaced with new value.


4. In List, we can access objects by using index, which is zero based. ie index of
first object is zero.
4. In Dict, we can access values by using keys.

5. In List, objects need not be hashable.
5. In Dict, key must be hashable.

Q9. What is the difference between List and Set?
Table: List Set
1. List is a group of comma separated individual objects within square brackets.
eg: 1= [10,20,30,40]
1. Set is a group of comma separated individual objects within curly braces.
eg: S= {10, 20,30, 40} 

Q9. What is the difference between List and Set?
Table: List Set
1. List is a group of comma separated individual objects within square brackets.
eg: 1= [10,20,30,40]
1. Set is a group of comma separated individual objects within curly braces.
eg: S= {10, 20,30, 40} 

2. Duplicate objects are allowed.
2. Duplicate objects are not allowed.

3. Insertion order is preserved.
3. Objects will be inserted based on hashcode and hence insertion order is not
preserved.

4. Objects need not hashable.
4. Objects should be hashable.

5. Indexing and Slicing concepts are applicable for List.
5. Indexing and Slicing concepts are not applicable for Set.


7. Tuple objects are hashable type and hence we can store in set and in dict as
keys.
s = {10,20,30, (40,50)} #Valid
s = { (10,20):'durga'} #Valid
T
•8. If the content is not fixed and keep on changing then it is recommended to go
for list objects.
eg: To store youtube comments
8. If the content is fixed and never changes then we should go for tuple objoets.
eg: Allowed input values for vendor machine.


07. What is the difference between Set and FrozenSet?
All properties of set and frozenset are same except the following difference:

https://www.includehelp.com/python/


***Q13. What is the difference between *args and **kwargs?
*args ---›Variable length arguments
f(*args)
If a function with *args arugment, then we can call that function by passing any
number of values including zero number.

def f1 (*args):
print(args
F1 ( )
F1 (10)
F1(10, 20)
F1 (10, 20, 36) all up/forp
•/p:
( )
(10,)
(10, 20)
(10, 20,
30)
18

def sum(*args) :
total=0
for x in args:
total = total+x
print ('The Sum:',total)
Sumi()
sum(10)
sum(10, 20)
sum (10, 20,30)

**kwargs ---›Variable length keyword arguments.
f1(**kwargs):
We can call this function by passing any number of keyword arguments including
zero number and with all these keyword arguments, a dictionary will be created.

a def f1 (**kwargs) :
print(kwargs)
f1 (name= 'Durga'‚rollno=100,marks=90)
0/p:


Q. What is the difference between dir) and help() function?
dir () function just list out all members of given module. But help() function
provides documentation related to that module.

import math
print (dir (math))
0/p:
[' doc
3
loader
name
package
_spec
"', 'acos'
'acosh'
'asin',
'asinh', 'atan'
'degrees', 'dist'.
'e'
3
'erf',
)

Note:
.....
dir () ----›Without argument, it will list out all members of current module.
dir (modulename) ----›with argument, it will list out all members of specifie
module.
eg:
x = 10
y = 20
def f1 ():
pass
print (dir ())

Q. What is Lambda Function or Anonymous Function?
Sometimes we can declare a function without any name, such type of nameless
functions are called anonymous functions or lambda functions.
The main bbiective of anonymous function is just for instant use.
Normal Function:
We can define normal function by using def keyword.

Normal Function:
....-
------.
We can define normal function by using def keyword.
• def squareit (n):
return n*n
Lambda Function:
We can define anonymous function by using lama keyword.
lambda

Lambda Function:
- ...
We can define anonymous function by using lama keyword.
lambda n: n*n
syntax:
Lambda argument_ list: expression

By using lambda functions, we can write very concise code, so that readability of
the code will be improved.

eg: create a lambda function to find square of given number?

s = lambda n: n*n
print ('The Square of 4:',s (4))
print ('The Square of 5:',s (5))

IQ. What are various differences between Normal function and Lambda Function?
Table: Normal Function Lambda Function
1. It is a named function and we can define by using def keyword.
1. It is a nameless (anonymous) function and we can define by using lambda keyword.
2. We have to write return statement expliticly to return some value.
2. We are not required to write return statement explicitly to return some value
because lambda function internally has return statement.

3. If we want to use a function multiple times, then we should go for normal
function.
3. If we want a function just for instant use(ie one time usage), then we should
go for lambda function.
4. Length of the code is more and hence readability will be reduced.
4. Length of the code is very less(concise code) and hence readability will be
improved.

Q. Explain about filter() function?
We can use filter() function to filter values from the given sequence based on
some condition.
filter (function, sequence)
Where argument function is responsible to perform conditional check and it should
be boolean valued function.

For every element in the given sequence, this function will be applied and if it
returns True then only the value will be consider in the result.
• without lambda function:
def is even (x):
if ×%2 == 0:
return True
else:
return False
11 = [0,5, 10, 15,20, 25,30]
l2=list(filter (is_even, 11))

11 = [0,5,10, 15, 20, 25,30]
12 = list(filter (lambda x: X%2 == 0,11))
print (12) #[0, 10, 20, 30]

11 = ['Apple'
" 'A'.
" 'AA', 'BBBB'.
, 'AppleApple'.
, 'BananaBanan ']
12 = list(filter (lambda s: len(x) › 5,11))
print (12)

11 = ['Apple', 'A'.
'A', 'AA', 'BBBB', 'AppleApple', 'BananaBanan ']
f = lambda s: len(s) >5
12=[]
for × in 11:
if f(x) == True:
12.append(x)
print(12)


Features of Python:
1. Simple and easy to learn
------------
2. Free ware and Open Source
3. High Level Programming Language
4. Platform independent
5. Portability
*****6. Dynamically Typed
7. Both Procedure Oriented and Object Oriented
8. Interpreted
9. Extensible
BI we have some code in java(1 Lakh lines of code)
We can improve performance of the application
10. Embedded:
We can use Python program

Backend web development framework
Freeware and Open Source
Completely developed by using Python
 Top 5 Features of Django Framework:
1. Fast
2. Fully Loaded
authentication, security, session management
admin
3. Security
CSRE
{%csrf_token%}
4. Scalability
5. Versatile
> Output - 



```
```
##  Inhrtitance 

```python

## 1. Write An SQL Query To Fetch Unique Values Of DEPARTMENT From Worker Table.  
SELECT DISTINCT DEPARTMENT
FROM employee;

##   2. Write An SQL Query To Print The FIRST_NAME And LAST_NAME From Worker Table Into A Single Column COMPLETE_NAME. A Space Char Should Separate Them.   
SELECT CONCAT(FIRST_NAME, ' ', LAST_NAME) AS COMPLETE_NAME
FROM Worker;

 ##  3. Write An SQL Query To Fetch The No. Of Workers For Each Department In The Descending Order.  
SELECT department, COUNT(worker_id) AS num_workers
FROM employees
GROUP BY department
ORDER BY num_workers DESC;

## 4.  Write An SQL Query To Print Worker Name and his/her manager name.
SELECT w.worker_name, m.worker_name as manager_name
FROM workers w
JOIN workers m ON w.manager_id = m.worker_id;


## 5.  Write a query to find the emp who is earning the highest salary under each department.
SELECT worker_ID, MAX(Salary) FROM EmpDetails GROUP BY DeptID

============

## 1. Write a program to sort the following array/list by ascending to descending without using inbuilt functions (like sort, max).  


23 , 21, 5, 43, 83, 231, 21
def arr_sort(arr):
    n = len(arr)
    for i in range(n):
        for j in range(0, n-i-1):
            if arr[j] < arr[j+1]:
                arr[j], arr[j+1] = arr[j+1], arr[j]

# Example usage:
my_list = [23 , 21, 5, 43, 83, 231, 21]
arr_sort(my_list)

print("Sorted list in descending order:")
print(my_list)



## 2. Write a program to find 2nd max value without using inbuilt functions (like sort, max) in the above array.   

def find_second_max(arr):
    max_value = float('-inf')
    second_max_value = float('-inf')

    for num in arr:
        if num > max_value:
            second_max_value = max_value
            max_value = num
        elif num > second_max_value and num != max_value:
            second_max_value = num

    if second_max_value == float('-inf'):
        return "No second maximum found"

    return second_max_value


arr = [23 , 21, 5, 43, 83, 231, 21]
second_max = find_second_max(arr)
print("Second maximum:", second_max)





## 3.Write a program to hit the api and fetch the result which is in json/dict format and print the selected key’s value which is a list in the sample output format.  


import requests
api_url = "https://abcxyz.com/input.json"
response = requests.get(api_url)
if response.status_code == 200:
    data = response.json()
    if data:
        for student_id, student_info in data.items():
            student_name = student_info.get("name", "N/A")
            subjects = student_info.get("subjects", [])
            print(f"Student ID: {student_id}")
            print(f"Student Name: {student_name}")
            print("Subjects:")
            for subject in subjects:
                print(f"- {subject}")
            print()
    else:
        print("No data available in the response.")
else:
    print(f"Failed to retrieve data. Status code: {response.status_code}")
    
    ====
    
## 1.Print all lines of a file which doesn’t contain the word “abc”. 
Sample Input File : 
Hello my name is abc 
I stay in Bangalore 
My full name is abc 

with open('sample.txt', 'r') as file:
    for line in file:
        if 'abc' not in line:
            print(line, end='')

grep -v 'abc' sample.txt

## 2.Print all lines matching the complete word “abc”.        

Sample Input File : 
Hello my name is abc 
I stay in Bangalore 
My full name is abcdef   
grep -w "abc" your_input_file.txt


## 3. Count the number of lines in a given file (file name: order_details.csv).   

wc -l order_details.csv

  4. Fetch the last 100 lines of a log file whose name is “application.log”.  
  tail -n 100 application.log
  
  5. Given a word “Exception” , print the 10 lines before and after this occurrence.  
  
  grep -n -B 10 -A 10 "Exception" your_file.txt
  
















> Output - 



```
```
## Take string as return interger sum

```python
def sum_of_integers(string):
    total = 0
    for char in string:
        if char.isdigit():
            total += int(char)
    return total


input_string = input("Enter an integer as a string: ")
result = sum_of_integers(input_string)
print("Sum of integers:", result)


> Output - 



```
```
##  Inhrtitance 

```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def display(self):
        print("Name:", self.name)
        print("Age:", self.age)

# Creating objects of Person class
person1 = Person("John", 25)
person2 = Person("Alice", 30)

# Calling the display method
person1.display()
person2.display()


> Output - 



```
#find out commomn string 
def common_letter():
  str1 = input("ENter first string")
  str2 = input("ENter second input")
  str1 = set(str1)
  str2 = set(str2)
  print(str1.intersection(str2))

  result = str1 & str2
  print(result)
common_letter()

```
