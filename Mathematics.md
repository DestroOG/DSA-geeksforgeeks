## Mathematics
### Sum of natural Numbers
Q) same question find sum of first n numbers

```
n=int(input("Write Number:"))

sum = 0
for i in range (1,n+1):
  sum = sum + i

print(sum)
```

now a better way: sum of first n number (mathematically) = n*(n+1)/2, so use this for your question

```
n=int(input("Emter Number: "))
sum=n*(n+1)/2
print(sum)
```

This code is so much better as its rate of growth is constant and its asymptotically better as well.
#### Problem 1: 
You are given an interger **I**, find the absolute value of the interger **I**.

**Example 1:**

**Input**:
I = -32
**Output:** 32
**Explanation:** 
The absolute value of -32 is 32.
```
class Solution:
    def absolute(self,I):
        if I < 0:
            return (-1*I)
        else:
            return I
```

#### Problem 2: Convert to Fahrenheit
Given a temperature in celsius **C**. You need to convert the given temperature to **Fahrenheit**.

**Example 1:**

**Input:**
C = 32
**Output:** 89
**Explanation:** Using the conversion 
formula of celsius to farhenheit , it
can be calculated that, for 32 degree
C, the temperature in Fahrenheit = 89

```
class Solution:
    ##Complete this function
    def cToF(self,C):
        F=(C*9/5)+32
        return F
```

### Count of numbers

Concepts used:
- We divide by 10 till we get result 0.x or 0 and count the number of times we did division
- We use // 
 Integer division
     Integer division in Python is a division operation where the result is the quotient of the division, rounded down to the nearest integer. It's denoted by using `//` between two numbers.
    For example:
     pythonCopy code
     `result = 7 // 3`
     In this case, `7` divided by `3` is equal to `2.3333...`, but when you use integer division (`//`), the result will be `2`. It discards the fractional part and gives you the largest integer that's less than or equal to the result.
     Here are a few more examples:
     pythonCopy code
     `10 // 3  # Result: 3 -10 // 3  # Result: -4 (rounded towards negative infinity)`     Integer division is useful when you want to divide two numbers and get the result as an integer, truncating any decimal part. It's particularly handy when you're working with situations where only whole numbers make sense, such as counting items or partitions of items into equal groups.

```
n=int(input("Enter Number: "))

ans=0

while n>0:
  n=n//10
  ans=ans+1

print("Count of digits =", + ans)
```

### Palindrome Number

==nai karra mai, fuck off==

### Factorial of a number

```
def fact(n):
  if n == 0:
    return 1
  else:
    return n*fact(n-1)

n=int(input("Enter number: "))

ans=fact(n)

print(f"The Factorial of {n} is {ans}")
```

#### Using loops (Iteration)

```
# Using Loops (Iteration)

def factorial_iterative(n):
    result = 1
    for i in range(1, n + 1):
        result *= i # result = rsult * i
    return result

# Input: Get the number from the user
n = int(input("Enter a number: "))

# Calculate the factorial using the iterative approach
fact = factorial_iterative(n)

# Output: Print the factorial
print(f"The factorial of {n} is {fact}")
```

### ==Count of numbers in a Factorial

This shit crazy

##### Attempt 1 (wrong code):

```
class Solution:
    def digitsInFactorial(self,N,m):
        m = 1
        for i in range(1, N + 1):
            m *= i
        ans=0
        while m>0:
            m=m//10
            ans=ans+1
        return ans
```

What was wrong: just had to remove m from def 

##### Attempt 2 (corrected code):

```
class Solution:
    def digitsInFactorial(self, N):
        factorial = 1
        for i in range(1, N + 1):
            factorial *= i
        ans = 0
        while factorial > 0:
            factorial = factorial // 10
            ans = ans + 1
        return ans
```

What was wrong: Time Limit Exceeded, Test cases: 20 / 220

##### Attempt 3 (Optimized code)

```
class Solution:
    def digitsInFactorial(self, N):
        m = 1
        for i in range(1, N + 1):
            m *= i
        count = len(str(m))
        return count
```

What was wrong:  Time Limit Exceeded, Test cases: 120 / 220
Basically for larger number the factorial will have a huge number and most languages cannot store that 
So what do we do

#### Attempt 4 (View solution)
Article: [[DSA GFG Articles#Count of digits in factorial (editorial article)]] 
Concepts used: 
 - The $\log_{10}X$ of any number below 10 is 0.x, for 100 its 1.x, for 1000 it is 2.x and so on
 - Floor of $\log_{10}X$ returns 0.x as 0, 1.x as 1 an so on
 - No of digits will be floor(logx)+1

![[Pasted image 20230920102804.png]]
![[Pasted image 20230920103542.png]]

```
import math 
class Solution:
    def digitsInFactorial(self, N):
      sum=0.0
      j=1
      while (j<=N):
          sum+=(math.log10(j))
          j+=1
      return 1+math.floor(sum)
      
```

Here's the explanation of the code step by step:
    1. The `math` module is imported, which is necessary for using the `log10` function.
    2. A class named `Solution` is defined, which contains a method named `digitsInFactorial`. This method takes an integer `N` as input.
    3. `sum` is initialized to `0.0`. This variable will be used to store the sum of logarithms of numbers from 1 to `N`.
    4. `j` is initialized to `1`. This variable is used as a counter to iterate through numbers from 1 to `N`.
    5. A `while` loop is used to calculate the sum of logarithms of numbers from 1 to `N`. The loop continues until `j` is less than or equal to `N`.
    6. Inside the loop:
    - `math.log10(j)` calculates the base-10 logarithm of the current valueof`j`.
    - `sum` is updated by adding this logarithm to it.
    - `j` is incremented to move to the next number in the sequence
    7. After the loop, the code calculates the number of digits in the factorial:
    - `1 + math.floor(sum)` adds 1 to the sum and rounds down the result to the nearest integer using `math.floor()`. This gives the total number of digits in the factorial of `N`.
    8. The result, which represents the number of digits in `N!`, is returned.
    So, the code efficiently calculates the number of digits in the factorial of `N` by summing the logarithms of the numbers from 1 to `N` and then rounding down the result. This avoids the need to compute the actual factorial, making it more efficient for large values of `N`.

### Trailing zeros 
==maa kasam==
```
def countzeros(n):
  i=5
  while(i<n):
    res=res+n//i
    i=i*5
  return res
```
![[Pasted image 20230920120339.png]]

### HCF or GCD 

```
def HCF(a,b):
  while(a!=b):
    if a>b:
      a=a-b
    else:
      b=b-a
  return a

a=int(input("a: "))
b=int(input("b: "))

result=HCF(a,b)
print(f"HCF of {a} and {b} is {result}")
```
![[Pasted image 20230920123315.png]]

##### Optimized:
==i aint doing this shit==
![[Pasted image 20230920124558.png]]

