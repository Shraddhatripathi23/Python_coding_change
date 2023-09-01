# Python Coding Interview Questions

<!-- Feature Image -->
| ![space-1.jpg](https://dyclassroom.com/image/topic/python/logo.png) | 
|:--:| 
| Image Credits [DY Classroom](https://dyclassroom.com/python/python-introduction) |

<!-- Content-->

## 1. Converting an Integer into Decimals

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
