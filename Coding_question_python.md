# Python Coding Interview Questions


<!-- Content-->

## 1. Second higest element in List without build in function

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

## 1. Inhrtitance 
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

``python
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

