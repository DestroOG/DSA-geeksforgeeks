## List

### Introduction 
- lists in python are array based 
- Dynamic in size 

```
l=[12,15,24,35,59]

print(l)
print(l[3])
print(l[-2])
print(l[-1])
```

![[Pasted image 20230921101205.png]]
Index should be used carefully, because if the item is not present in the list it will call value error. So always check if the item exist in the list first using in function and then index the item


![[Pasted image 20230921101720.png]]
Similar caution for remove function


![[Pasted image 20230921101917.png]]
max min sum sort function will not work if u have different datatypes in the list 

### Working of list in python 

[[DSA GFG Articles#Introduction to lists and working of lists in python]]


### Problem
You are given an array **arr**(0-based indexing). The size of the array is given by **n**. You need to **get** the element at **index i** and return it. If **no** element exists at **i** then **return -1**.

**Example 1:**

**Input:**
n = =6
arr[] = {1 2 3 4 5 6}
index = 0
**Output:** 1
**Explanation:** The array is {1 2 3 4 5 6}.
The index given is 0. so element at 0th
index is 1.

**Your Task:**  
This is a function problem. The input is already taken care of by the driver code. You only need to complete the function **getByIndex()** that takes _arr_**,** _n_**,** _i_ as input and **return** the required result. The **driver code** takes care of the **printing**.

**Expected Time Complexity:** O(1).  
**Expected Auxiliary Space:** O(1).

**Constraints:**  
1 <= n<= 103  
0 <= arri <= 106  
1 <= index <= 106
#### Answer: 
```
def getByIndex(arr,n,idx):
    if idx < n:
        return (arr[idx])
    else:
        return("-1")
```


==Solved 5 prob, all perf no issues==

### Average/Mean of List
ez
```
l=[12,15,24,35,59]
avg=sum(l)/len(l)
print(avg)
``` 

### Problem: Mean and Median of Array
Given an array **a[ ]** of size **N**. The task is to find the **median** and **mean** of the array elements. Mean is average of the numbers and median is the element which is smaller than half of the elements and greater than remaining half.  If there are odd elements, the median is simply the middle element in the sorted array. If there are even elements, then the median is floor of average of two middle numbers in the sorted array. If mean is floating point number, then we need to print floor of it.

**Note:** To find the **median**, you might need to **sort** the array. Since sorting is covered in later tracks, we have already provided the sort function to you in the code.

**Example 1:**

**Input:**
N = 5
a[] = {1, 2, 19, 28, 5}
**Output:** 11 5
**Explanation:** For array of 5 elements,
mean is (1 + 2 + 19  + 28  + 5)/5 = 11.
Median is 5 (middle element after 
sorting)

**Solution:**

```
import math
class Solution:
    ##Complete the below codes
    #Function to find median of the array elements.
    def median(self,A,n):
        
        A.sort()
        if n % 2 == 1:
            median = A[n // 2]  # For odd-sized lists, median is the middle value
        else:
            middle1 = A[(n - 1) // 2]
            middle2 = A[(n + 1) // 2]
            median = (middle1 + middle2) / 2  # For even-sized lists, median is the average of the two middle values
        return math.floor(median)
        #If median is fraction then convert the median to integer and return
     
    #Function to find mean of the array elements.   
    def mean(self,A,N):
        avg=sum(A)/N
        return(math.floor(avg))
```

### Separate even and odd

```
l=[12,15,24,35,59,30,22,37]
e=[]
o=[]
for element in l:
  if element%2 != 0:
    e.append(element)
  else:
    o.append(element)

print(e,o)
```


### Get smaller elements from list

```
l=[12,15,24,35,59,30,22,37]
x=25
s=[]
for i in l:
  if i<x:
    s.append(i)

print(s)
```

### Problem: Immediate smaller element from list

#### Attempt 1: Wrong
```
class Solution:
    def immediateSmaller(self,arr,n,x):
        arr.sort(reverse=True)
        for i in arr:
            if i<x:
                return i
```
What was wrong: This returns the smallest element, we need immediate smaller element

#### Attempt 2: Runtime error
```
class Solution:
    def immediateSmaller(self,arr,n,x):
        s=[]
        for i in arr:
            if i<x:
                s.append(i)
        return max(s)
```
What was wrong: the code is correct but there are no smaller elements s will be empty and max(s) will return with a runtime error.
To fix this we must first check if len(s) !== 0
#### Attempt 3: Correct solution

```
class Solution:
    def immediateSmaller(self,arr,n,x):
        s=[]
        for i in arr:
            if i<x:
                s.append(i)
        if len(s) == 0:
            return -1
        else:
            return max(s)
```

### Problem: Who has majority

Given an array **arr[]** of size **N** and two elements **x** and **y**, use counter variables to find which element appears most in the array. If both elements have the same frequency, then return the smaller element.  
**Note:**  We need to return the element, not its count.

**Example 1:**

**Input:**
N = 11
arr[] = {1,1,2,2,3,3,4,4,4,4,5}
x = 4, y = 5
**Output:** 4
**Explanation:** 
frequency of 4 is 4.
frequency of 5 is 1.


#### Attempt 1: Oonga Boonga Code

```
from collections import counter
class Solution:
    #Function to find element with more appearances between two elements in an array.    
    def majorityWins(self, arr, n, x, y):
        for i in arr:
            f=i_count.most_common()
            if x=f:
                return x
            if y=f:
                return y
            else:
                if x<y:
                    return x
                else:
                    return y
    
```
What was wrong: umm..many things
1) import Counter* (capital C)
2) thats not how u use counter, you first create an object that counts no of each elements in array and then define which values you want to count and compare
3) thats not how you write multiple if statements, you use if elif elif then else
4) wtf was that else statement, min(x,y) is how you find which of them are smaller

#### Attempt 2: Corrected code (YOGI AI BOT)
```
from collections import Counter
class Solution:
    #Function to find element with more appearances between two elements in an array.    
    def majorityWins(self, arr, n, x, y):
        counter = Counter(arr)
        x_count = counter[x]
        y_count = counter[y]
        
        if x_count > y_count:
            return x
        elif y_count > x_count:
            return y
        else:
            return min(x, y)
```

Code explanation
    1. Import the `Counter` class from the `collections` module. `Counter` is used to count the occurrences of elements in a collection.
    2. Define the `Solution` class.
    3. Define the `majorityWins` method within the `Solution` class. It takes the following parameters:
    - `arr`: The input array in which you want to find the majority element.
    - `n`: The number of elements in the array (though this parameter is not used in the code).
    - `x`: The first element you want to compare.
    - `y`: The second element you want to compare.
    4. Create a `Counter` object named `counter` by passing the `arr` as an argument. This object will count the occurrences of each element in `arr`.
    5. Calculate the counts of elements `x` and `y` using the `counter` object:
    - `x_count = counter[x]`: The count of occurrences of element `x`.
    - `y_count = counter[y]`: The count of occurrences of element `y`.
    6. Compare the counts of `x` and `y` to determine the majority element:
    - If `x_count` is greater than `y_count`, it means `x` appears more frequently, so the method returns `x`.
    - If `y_count` is greater than `x_count`, it means `y` appears more frequently, so the method returns `y`.
    - If the counts are equal, the method returns the minimum of `x` and `y`.
    - The code essentially leverages the `Counter` class to count the occurrences of `x` and `y` in the `arr` array and then compares the counts to find the majority element, returning the result.
-


### Slicing List, Tuple and String

**Syntax :**

> _string[start : end : step]_
> 
> - _start : We provide the starting index._
> - _end : We provide the end index(this is not included in substring)._
> - _step : It is an optional argument that determines the increment between each index for slicing._

_**Example:**_ 

Python3

```python3

# declaring the string
str ="Geeks for Geeks !"
 
# slicing using indexing sequence
print(str[: 3])
print(str[1 : 5 : 2])
print(str[-1 : -12 : -2])
```
**Output**
Gee
ek
!seGrf



Note:
Only difference between list tuple and string is, if u make a new list (l2) with same values it will be saved as a new list. This is not the case for tuple and string. If new tuple/string has same value, python will return reference to the same tuple/string

![[Pasted image 20230922095605.png]]

### Comprehensions in python 

![[Pasted image 20230922103003.png]]


#### Using comprehension method for previous questions

```
# Q) Return a list conatining all items smaller than x

def getsmaller(l,x):

  return[e for e in l if e<x]

  

l=[3,5,1,34,4,8,12,13]

x=10

  

print(getsmaller(l,x))
```

![[Pasted image 20231117111655.png]]

```
# Q) return a list containing all even and odd eleemnts

def oddeve(l):

  even=[x for x in l if x%2==0]

  odd=[x for x in l if x%2 != 0]

  return even,odd

l=[4,2,1,3,6,7,8,9,10]

even,odd=oddeve(l)

print(even)

print(odd)
```

#### Dictionary comprehension
![[Pasted image 20231117113003.png]]

Inverted Dictionary:
![[Pasted image 20231117113144.png]]

##### [Comprehensions in python article](https://practice.geeksforgeeks.org/batch/ds-with-python/track/list-basic-python/article/NjE2Mg%3D%3D)

### Largest element in list
Direct apporach:
`print(max(l1))`

#### Attempt 1: Wrong code, retarded logic
```
def largest(l):

  return[x for x in l if x-x>0]

  

l=[1,2,3,4,5]

print(largest(l))
```
Idek what how to say what is wrong

#### Attempt 2: ChatGPT 
```
def largest(l):

  large=l[0]

  for x in l:

    if x>large:

      large=x

  return large

  

l=[1,2,3,4,5]

print(largest(l))
```

### Simple method
bruh time comlexity and shit 

they also talked about one more solution with linear time complexity
check [article](https://practice.geeksforgeeks.org/batch/ds-with-python/track/list-basic-python/article/NjE2Mw%3D%3D) for more

### Problem: Maximum and Minimum in array

```
def maximumElement(arr,n):
    lar=arr[0]
    for n in arr:
        if n>lar:
            lar=n
    return lar



def minimumElement(arr,n):
    smol=arr[0]
    for n in arr:
        if n<smol:
            smol=n
    return smol
```

![[Pasted image 20231117115738.png]]

### Second Largest Element in listing

```
def p2largest(arr, arrsize):

  if arrsize<2:

    print("Invalid Size")

    return

  

  largest = second = -8898900917289 #initializing largest an second largest to a very small number

  

  for i in range(0,arrsize):

    largest = max(largest, arr[i])

  for i in range(0,arrsize):

    if arr[i]!= largest:

      second = max(second, arr[i])

  

  if second == -8898900917289:

    print("There is no second largest element")

  else:

    print("The second largest element is: ",second)

  # Driver code

if __name__ == '__main__':

    arr = [12, 35, 1, 10, 34, 1]

    n = len(arr)

    p2largest(arr, n)
```

### Problem: Is array sorted

check if array is sorted, both asc and describe
```
class Solution:
    def isSorted(self,arr,n):
        iarr=sorted(arr)
        darr=sorted(arr, reverse=True)
        
        if arr == iarr:
            return 1
        elif arr == darr:
            return 1
        else:
            return 0
```

202/202 in first attempt 

### Reverse a list
![[Pasted image 20231119144349.png]]
**Method 2: Using two pointer approach**

Python

```python
def reverseList(l):
    s = 0
    e = len(l) - 1

    while s < e:
        l[s], l[e] = l[e], l[s] # swapping left element to right and right element to left
        s = s + 1
        e = e - 1



l = [int(x) for x in input().split(',')]
reverseList(l)
print(l)
```

### Removing duplicates
![[Pasted image 20231119145625.png]]
#### Optimized method
```
def remdup(arr,n):
  res=1
  for i in range(1,n):
    if (arr[res-1]!=arr[i]):
      arr[res]=arr[i]
      res+=1

    return res
```
==but umm...this return only len of the array how to get the array without duplicates==

I asked GPT and got this
```
def remdup(arr, n):
    res = 1
    for i in range(1, n):
        if arr[res - 1] != arr[i]:
            arr[res] = arr[i]
            res += 1
    return arr[:res]

arr = [2, 3, 4, 4, 5, 6, 7, 7, 8, 9, 9, 9, 0]
n = len(arr)
result = remdup(arr, n)
print(result)

```

### Left Rotate a List
