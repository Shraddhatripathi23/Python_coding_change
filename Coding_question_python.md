# Python Coding Interview Questions


<!-- Content-->


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

##  Inhrtitance 

```python


> Output - 



```

##  Inhrtitance 

```python


> Output - 



```

##  Inhrtitance 

```python


> Output - 



```
##  Inhrtitance 

```python


> Output - 



```
##  Inhrtitance 

```python


> Output - 



```
##  Inhrtitance 

```python


> Output - 



```
