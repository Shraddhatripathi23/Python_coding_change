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

## 1. Inhrtitance 
#Single Inheritance 

```python

> 90
> 89

```
