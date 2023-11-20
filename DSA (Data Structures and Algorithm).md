# DSA in Python [Geeks For Geeks] course

This course contains videos, articles, quizes and challenges. From module 3 (Mathematics) i will be writing my notes in here whereas the article copy pastes in google docs or in [[DSA GFG Articles]] 
#### Basics:

## DSA: What, Why and How?
#### What
- Data Structures: The way to organize data in main memory or ram
- Algorithm: sequence of steps you write to solve a problem

#### Why
- Makes you a better software developer
- ==Helps you in getting a job==
- Winning the sport of computer coding

#### How (Road Map)
1) Learn a programming language
2) Learn DSA basics and implement
3) Learn language libraries that have DSA implemented for you
4) Practice and learn together


## Analysis Of Algorithm 
### Background
#### Q1) Sum of n natural numbers 
(damn im so dumb, idek how to do this shit)

I tried: ![[Pasted image 20230918123701.png]]

ChatGPT and sir helped:
![[Pasted image 20230918124457.png]]

#### What is meant by Algorithm Analysis?

Algorithm analysis is an important part of computational complexity theory, which provides theoretical estimation for the required resources of an algorithm to solve a specific computational problem. Analysis of algorithms is the determination of the amount of time and space resources required to execute it.

#### Why Analysis of Algorithms is important?

- To predict the behavior of an algorithm without implementing it on a specific computer.
- It is much more convenient to have simple measures for the efficiency of an algorithm than to implement the algorithm and test the efficiency every time a certain parameter in the underlying computer system changes.
- It is impossible to predict the exact behavior of an algorithm. There are too many influencing factors.
- The analysis is thus only an approximation; it is not perfect.
- More importantly, by analyzing different algorithms, we can compare them to determine the best one for our purpose.

#### Types of Algorithm Analysis:

1. Best case
2. Worst case
3. Average case


![[Pasted image 20230918125533.png]]

#### Asymptotic Analysis
    - No Dependancy on machine
    - We do not have to implement all ideas/algorithms
    - Measuring order of growth in input size

It is important to analyze an algorithm after writing it to find it's efficiency in terms of time and space in order to improve it if possible. 

When it comes to analyzing algorithms, the asymptotic analysis seems to be the best way possible to do so. This is because asymptotic analysis analyzes algorithms in terms of the input size. It checks how are the time and space growing in terms of the input size.

In this post, we will take an example of Linear Search and analyze it using Asymptotic analysis.

We can have three cases to analyze an algorithm:

1. Worst Case
2. Average Case
3. Best Case

Below is the algorithm for performing linear search:

Python

```python
# Searching an element in a list/array in python
# can be simply done using \'in\' operator
# Example:
# if x in arr:
# print arr.index(x)

# If you want to implement Linear Search in python

# Linearly search x in arr[]
# If x is present then return its location
# else return -1

def search(arr, x):

	for i in range(len(arr)):

		if arr[i] == x:
			return i

	return -1
```

**Worst Case Analysis** **(Usually Done):** In the worst case analysis, we calculate upper bound on running time of an algorithm. We must know the case that causes the maximum number of operations to be executed. For Linear Search, the worst case happens when the element to be searched (x in the above code) is not present in the array. When x is not present, the search() functions compares it with all the elements of arr[] one by one. Therefore, the worst case time complexity of linear search would be  O(N), where N is the number of elements in the array.

**Average Case Analysis** **(Sometimes done):**  In average case analysis, we take all possible inputs and calculate computing time for all of the inputs. Sum all the calculated values and divide the sum by total number of inputs. We must know (or predict) distribution of cases. For the linear search problem, let us assume that all cases are uniformly distributed (including the case of x not being present in array). So we sum all the cases and divide the sum by (N+1). Following is the value of average case time complexity..

![](https://media.geeksforgeeks.org/wp-content/uploads/20220929182316/D540-300x136.png)

**Best Case Analysis (Bogus):** In the best case analysis, we calculate lower bound on running time of an algorithm. We must know the case that causes minimum number of operations to be executed. In the linear search problem, the best case occurs when x is present at the first location. The number of operations in the best case is constant (not dependent on N). So time complexity in the best case would be O(1)

**Important Points:**

- Most of the times, we do the worst case analysis to analyze algorithms. In the worst analysis, we guarantee an upper bound on the running time of an algorithm which is a good piece of information.
- The average case analysis is not easy to do in most of the practical cases and it is rarely done. In the average case analysis, we must know (or predict) the mathematical distribution of all possible inputs.
- The Best Case analysis is bogus. Guaranteeing a lower bound on an algorithm doesn't provide any information as in the worst case, an algorithm may take years to run.

#### Order of Growth
 >Fun(1) --> $C1$ (constant growth)
   fun(2) --> $C2n + C3$ (linear growth)
   fun(3) --> $C4n^2 + C5n + C6$ (quadrilateral growth)

![[Pasted image 20230918131730.png]]


### Order of Growth

**![](https://lh4.googleusercontent.com/tOjIBKWRRTEQdc5WDfMoc5ohWo_V7fFf1wGD3h9Sg7YrZt6OTGn2sm2BDvhPC_IdJucL-FHUO1GdObUoE1SWjQyHADJJYqb0ah_UV6ehefvz0O9md5DAo8Kg777YgPyHL8ymUeqztQvgP1KmKhCxkNg)**

**![](https://lh4.googleusercontent.com/m1vXj_GnENJt0W5-eOMOqm41-Mkv8k3Zwbrd8_b6Qr9Op76SevnK5_w6ZPRbfKAHDlxLZHIU_zHtLuesA2iGdmgxYipCHrccUmaeZx1y2Na9ah-hKaAB9y7M5_dxShbm2UeDKqZIPflCrbkMJJSfdbg)**

### Big O Notation
Big O notation gives us an upper bound on order of growth 

Short cut method: Ignore lower order terms, ignore constants and you get big o notation 
> Example:
> $$ f(n) = 4x^2 + 4n + \log n + 30 $$
> here we ignore 4n, log n, 30 and also 4 we directly get $f(n)= O(n^2)$ as big O notation of then function


We say $f(n) = 0(g(n))$ if there exist a constant C and N0  such that $$ f(n) \leq c*g(n)$$ for all N > N0 

>Example:
>nai karra, short cut enough

### Omega notation
Gives us lower bound 

![[Pasted image 20230918163418.png]]

same as Big O, instead of $O(n^2)$ we write $\Omega (n^2)$ 

If $f(n) = \Omega(g(n))$ then $g(n) = O(f(n))$ 

### Theta Notation 
Is used to represent ==Exact Bound==. Whenever you know exaxt bound prefer to use theta notation 

![[Pasted image 20230918164437.png]]

$$1000n^2+100n\log n+2n:\theta(n^2)$$ $$200n^3+30n+5:\theta(n^3)$$
$$2000n+2\log n:\theta(n)$$
We have discussed Asymptotic Analysis, and Worst, Average, and Best Cases of Algorithms. The main idea of asymptotic analysis is to have a measure of the efficiency of algorithms that don’t depend on machine-specific constants and don’t require algorithms to be implemented and time taken by programs to be compared. Asymptotic notations are mathematical tools to represent the time complexity of algorithms for asymptotic analysis. The following 3 asymptotic notations are mostly used to represent the time complexity of algorithms.   
  
![](https://media.geeksforgeeks.org/wp-content/cdn-uploads/20220521131928/3418.png)  
  
**1) Θ Notation:**  
  
The theta notation bounds a function from above and below, so it defines exact asymptotic behavior.   
A simple way to get the Theta notation of an expression is to drop low-order terms and ignore leading constants. For example, consider the following expression.   
3n3 + 6n2 + 6000 = Θ(n3)   
Dropping lower order terms is always fine because there will always be a number(n) after which Θ(n3) has higher values than Θ(n2) irrespective of the constants involved.   
For a given function g(n), we denote Θ(g(n)) is following set of functions.   
  
  
Θ(g(n)) = {f(n): there exist positive constants c1, c2 and n0 such   
that 0 <= c1*g(n) <= f(n) <= c2*g(n) for all n >= n0}  
The above definition means, if f(n) is theta of g(n), then the value f(n) is always between c1*g(n) and c2*g(n) for large values of n (n >= n0). The definition of theta also requires that f(n) must be non-negative for values of n greater than n0.   
  
![](https://media.geeksforgeeks.org/wp-content/cdn-uploads/20220521132004/3518.png)  
  
  
**2) Big O Notation:**   
  
The Big O notation defines an upper bound of an algorithm, it bounds a function only from above. For example, consider the case of Insertion Sort. It takes linear time in the best case and quadratic time in the worst case. We can safely say that the time complexity of Insertion sort is O(n^2). Note that O(n^2) also covers linear time.   
  
If we use Θ notation to represent time complexity of Insertion sort, we have to use two statements for best and worst cases:   
1. The worst-case time complexity of Insertion Sort is Θ(n^2).   
2. The best case time complexity of Insertion Sort is Θ(n).   
  
The Big O notation is useful when we only have an upper bound on the time complexity of an algorithm. Many times we easily find an upper bound by simply looking at the algorithm.   
  
O(g(n)) = { f(n): there exist positive constants c and   
n0 such that 0 <= f(n) <= c*g(n) for   
all n >= n0}  
  
![](https://media.geeksforgeeks.org/wp-content/cdn-uploads/20220521132046/3619.png)  
  
  
**3) Ω Notation:**   
  
Just as Big O notation provides an asymptotic upper bound on a function, Ω notation provides an asymptotic lower bound.   
Ω Notation can be useful when we have a lower bound on the time complexity of an algorithm. As discussed in the previous post, the best case performance of an algorithm is generally not useful, the Omega notation is the least used notation among all three.   
  
For a given function g(n), we denote by Ω(g(n)) the set of functions.   
  
Ω (g(n)) = {f(n): there exist positive constants c and  
n0 such that 0 <= c*g(n) <= f(n) for  
all n >= n0}.  
Let us consider the same Insertion sort example here. The time complexity of Insertion Sort can be written as Ω(n), but it is not very useful information about insertion sort, as we are generally interested in worst-case and sometimes in the average case.   
  
  
**Properties of Asymptotic Notations :**  
  
As we have gone through the definition of these three notations let’s now discuss some important properties of those notations.   
  
**1. General Properties :**  
  
If f(n) is O(g(n)) then a*f(n) is also O(g(n)) ; where a is a constant.   
  
Example: f(n) = 2n²+5 is O(n²)   
then 7*f(n) = 7(2n²+5) = 14n²+35 is also O(n²) .  
  
Similarly, this property satisfies both Θ and Ω notation.   
  
  
We can say   
If f(n) is Θ(g(n)) then a*f(n) is also Θ(g(n)) ; where a is a constant.   
If f(n) is Ω (g(n)) then a*f(n) is also Ω (g(n)) ; where a is a constant.  
  
  
**2. Transitive Properties :**  
  
If f(n) is O(g(n)) and g(n) is O(h(n)) then f(n) = O(h(n)) .  
  
Example: if f(n) = n, g(n) = n² and h(n)=n³  
n is O(n²) and n² is O(n³)  
then n is O(n³)  
  
Similarly, this property satisfies both Θ and Ω notation.  
  
We can say  
If f(n) is Θ(g(n)) and g(n) is Θ(h(n)) then f(n) = Θ(h(n)) .  
If f(n) is Ω (g(n)) and g(n) is Ω (h(n)) then f(n) = Ω (h(n))  
  
  
**3. Reflexive Properties :**   
  
Reflexive properties are always easy to understand after transitive.  
  
If f(n) is given then f(n) is O(f(n)). Since MAXIMUM VALUE OF f(n) will be f(n) ITSELF !  
  
Hence x = f(n) and y = O(f(n) tie themselves in reflexive relation always.  
  
Example: f(n) = n² ; O(n²) i.e O(f(n))  
  
Similarly, this property satisfies both Θ and Ω notation.  
  
We can say that:  
  
If f(n) is given then f(n) is Θ(f(n)).  
  
If f(n) is given then f(n) is Ω (f(n)).  
  
  
**4. Symmetric Properties :**   
  
  
If f(n) is Θ(g(n)) then g(n) is Θ(f(n)) .   
  
  
Example: f(n) = n² and g(n) = n²   
then f(n) = Θ(n²) and g(n) = Θ(n²)   
  
  
This property only satisfies for Θ notation.  
  
  
**5. Transpose Symmetric Properties :**   
  
  
If f(n) is O(g(n)) then g(n) is Ω (f(n)).   
  
  
Example: f(n) = n , g(n) = n²   
then n is O(n²) and n² is Ω (n)   
  
This property only satisfies O and Ω notations.  
  
  
**6. Some More Properties :**   
  
1.) If f(n) = O(g(n)) and f(n) = Ω(g(n)) then f(n) = Θ(g(n))  
  
2.) If f(n) = O(g(n)) and d(n)=O(e(n))   
then f(n) + d(n) = O( max( g(n), e(n) ))   
Example: f(n) = n i.e O(n)   
d(n) = n² i.e O(n²)   
then f(n) + d(n) = n + n² i.e O(n²)  
  
3.) If f(n)=O(g(n)) and d(n)=O(e(n))   
then f(n) * d(n) = O( g(n) * e(n) )   
Example: f(n) = n i.e O(n)   
d(n) = n² i.e O(n²)   
then f(n) * d(n) = n * n² = n³ i.e O(n³)  
  
  
  
**Exercise:**   
  
Which of the following statements is/are valid?   
1. Time Complexity of QuickSort is Θ(n^2)   
2. Time Complexity of QuickSort is O(n^2)   
3. For any two functions f(n) and g(n), we have f(n) = Θ(g(n)) if and only if f(n) = O(g(n)) and f(n) = Ω(g(n)).   
4. Time complexity of all computer algorithms can be written as Ω(1)

**Answer:** Option 2,3 and 4 are valid


#### Analysis of common loops
==mujhe nai samjha==
**Analysis of Common Loops: While Loop in Python**

Loops are essential constructs in programming that allow us to repeat a block of code multiple times. Python offers several types of loops, and one of the most versatile is the **while** loop. The **while** loop continues to execute a block of code as long as a given condition remains true. In this article, we will analyze and demonstrate the use of the **while** loop for subtraction, multiplication, exponentiation, and nested loops in Python.

#### **Addition using a While Loop**

Let's begin by examining how to utilize a **while** loop for addition. The following code demonstrates a simple implementation of adding two numbers using a **while** loop:

Python3

```python3
def add(a, b):
    result = a
    while b > 0:
        result += 1
        print(result)
        b -= 1
    	

# Example usage
a = 10
b = 7
add(a,b)
```

  
**Output**

11
12
13
14
15
16
17

In the code above, we define a function called **add** that takes two numbers, **a** and **b**, as parameters. We initialize the variable **result** with the value of **a**. The **while** loop executes **b** times, incrementing the **result** by 1 on each iteration while decrementing **b** by 1. Finally, the function returns the added value.

**Time complexity analysis :**

**Addition using a While Loop:**

- Time Complexity: O(b)
- Similar to multiplication, the **while** loop executes **b** times, where **b** is the value being added. Thus, the time complexity is linear and proportional to **b**.

#### **Subtraction using a While Loop**

Let's start by examining how to use a **while** loop for subtraction. The following code demonstrates a simple implementation of subtracting two numbers using a **while** loop:

Python3

```python3
# code
def subtract(a, b):
    result = a
    while result >= b:
      print(result)
      result -= b
    	

# Example usage
a = 15
b = 7
subtract(a, b)

```

  
**Output**

15
8

In the code above, we define a function called **subtract** that takes two numbers, **a** and **b**, as parameters. We initialize the variable **result** with the value of **a**. The **while** loop continues subtracting **b** from **result** until **result** becomes less than **b**. Finally, the function returns the subtracted value.

**Time complexity analysis :**

**Subtraction using a While Loop:**

- Time Complexity: O(a / b)
- In the worst case scenario, the number of iterations required to subtract **b** from **a** using a **while** loop is **a / b**. This assumes that **a** is significantly larger than **b**. The time complexity is linear and depends on the magnitude of **a** and **b**.

#### **Multiplication using a While Loop**

Now let's explore how to perform multiplication using a **while** loop. The following code demonstrates a basic implementation of multiplying two numbers using a **while** loop:

Python3

```python3
def multiply(n, c):
    result = 1
    while result < n:
      print(result)
      result *= c
      

# Example usage
n =32 
c = 2
multiply(n, c)
```

  
**Output**

1
2
4
8
16

In the code above, we define a function called **multiply** that takes two numbers, n and 1, as parameters. We initialize the variable **result** with 0. The **while** loop executes upto result value is not greater thea n , multiply result with c Finally, the function prints the value of multiplication.

**Time complexity analysis :**

**Multiplication using a While Loop:**

1. **Let's say the number of iteration be K so the value be : 1,C,C^2,C^3,C^K-1**
2. **C^K-1< n**
3. **K<logn+1**
4. **Growth of order is O(logn)**

- **Time Complexity: O(logn)**

#### **Exponentiation using a While Loop**

Next, let's see how to perform exponentiation using a **while** loop. The following code demonstrates a basic implementation of calculating the exponentiation of a number using a **while** loop:

Python3

```python3
def exponentfun(n, c):
    result = 2
    while result < n:
      print(result)
      result =result** c
      

# Example usage
base = 2
exponent = 32
exponentfun(exponent,base)
```

  
**Output**

2
4
16

In the code above, we define a function called **exponentfun** that takes two numbers, **base** and **exponent**, as parameters. We initialize the variable **result** with 2. The **while** loop executes **exponent** times, multiplying the **result** by **base** on each iteration while result is not greater than n or exponent, Finally, the function returns the exponentiated value.

**Time Complexity  Analysis:**

**Exponentiation using a While Loop:**

1. **Time Complexity: O(loglogn)**
2. **if this function iterates K time then values comes up to be 2,2^C,(2^C)^C ... ((2^C)^2...))^C...**
3. **2^CK-1<n**
4. **C^K-1<log2n**
5. **k<loglogn+1**
6. **T=O(loglogn)**

-  **Time Complexity: O(loglogn)**

#### **Nested While Loops**

Python allows the usage of nested loops, including nested **while** loops. A nested loop is a loop within another loop. This type of loop structure can be useful for handling complex scenarios that require multiple iterations. Here's an example of a nested **while** loop:

> i = 0  
> while i <= 5:  
>    j = 1  
>    while j <= n:        
>        j *= 1    
>    i += 1

Some constant work is done in the nested loop.

> j = 1  
>    while j <= n:        
>        j *= 1 

1. **Time complexity of given nested loop  O(logn)** 
2. **In case of nested loop we do multiply time complexity of of both loops**
3. **T=O(n)*O(logn)=O(nlogn)**

**Nested While Loops:**

- **Time Complexity**: **O(nlogn)**

#### **Conclusion**

The **while** loop is a powerful construct in Python that allows us to repeat a block of code as long as a specific condition remains true. In this article, we explored the use of **while** loops for subtraction, multiplication, exponentiation, and nested loops. By leveraging the flexibility of the **while** loop, you can implement various algorithms and handle different scenarios efficiently. Keep in mind that while using **while** loops, it's essential to ensure the condition eventually becomes false to avoid infinite loops.

Mark as Read

Report An Issue
#### Analysis of Recursion 

Many algorithms are recursive. When we analyze them, we get a recurrence relation for time complexity. We get running time on an input of size n as a function of n and the running time on inputs of smaller sizes. For example in Merge Sort, to sort a given array, we divide it into two halves and recursively repeat the process for the two halves. Finally, we merge the results. Time complexity of Merge Sort can be written as T(n) = 2T(n/2) + cn. There are many other algorithms like Binary Search, Tower of Hanoi, etc.   
  
There are mainly three ways of solving recurrences:

#### Substitution Method: 

We make a guess for the solution and then we use mathematical induction to prove the guess is correct or incorrect. 

> For example consider the recurrence T(n) = 2T(n/2) + n
> 
> We guess the solution as T(n) = O(nLogn). Now we use induction to prove our guess.
> 
> We need to prove that T(n) <= cnLogn. We can assume that it is true for values smaller than n.
> 
> T(n) = 2T(n/2) + n  
>      <= 2c(n/2Log(n/2)) + n  
>        =  cnLogn - cnLog2 + n  
>        =  cnLogn - cn + n  
>     <= cnLogn

#### **Recurrence Tree Method:**

In this method, we draw a recurrence tree and calculate the time taken by every level of the tree. Finally, we sum the work done at all levels. To draw the recurrence tree, we start from the given recurrence and keep drawing till we find a pattern among levels. The pattern is typically arithmetic or geometric series.   
 

> For example, consider the recurrence relation 
> 
> T(n) = T(n/4) + T(n/2) + cn2
> 
>             cn2  
>             /      \  
>   T(n/4)     T(n/2)
> 
> If we further break down the expression T(n/4) and T(n/2),   
> we get the following recursion tree.
> 
>                     cn2  
>               /             \        
>     c(n2)/16          c(n2)/4  
>    /         \            /         \  
> T(n/16)  T(n/8)  T(n/8)    T(n/4) 
> 
> Breaking down further gives us following
> 
>                        cn2   
>                 /                \       
>        c(n2)/16              c(n2)/4  
>     /          \                 /          \  
> c(n2)/256  c(n2)/64  c(n2)/64   c(n2)/16  
>  /    \            /    \      /    \        /    \  
> 
> To know the value of T(n), we need to calculate the sum of tree   
> nodes level by level. If we sum the above tree level by level, 
> 
> we get the following series T(n)  = c(n^2 + 5(n^2)/16 + 25(n^2)/256) + ....  
> The above series is a geometrical progression with a ratio of 5/16.
> 
> To get an upper bound, we can sum the infinite series. We get the sum as (n2)/(1 - 5/16) which is O(n2)

#### **Master Method:** 

Master Method is a direct way to get the solution. The master method works only for the following type of recurrences or for recurrences that can be transformed into the following type.   
 

> T(n) = aT(n/b) + f(n) where a >= 1 and b > 1

  
There are the following three cases: 

- If f(n) = O(nc) where c < Logba then T(n) = Θ(nLogba) 
- If f(n) = Θ(nc) where c = Logba then T(n) = Θ(ncLog n) 
- If f(n) = Ω(nc) where c > Logba then T(n) = Θ(f(n)) 

##### **How does this work?** 

The master method is mainly derived from the recurrence tree method. If we draw the recurrence tree of T(n) = aT(n/b) + f(n), we can see that the work done at the root is f(n), and work done at all leaves is Θ(nc) where c is Logba. And the height of the recurrence tree is Logbn   
 

![Master Theorem](https://media.geeksforgeeks.org/wp-content/uploads/AlgoAnalysis.png)

  
In the recurrence tree method, we calculate the total work done. If the work done at leaves is polynomially more, then leaves are the dominant part, and our result becomes the work done at leaves (Case 1). If work done at leaves and root is asymptotically the same, then our result becomes height multiplied by work done at any level (Case 2). If work done at the root is asymptotically more, then our result becomes work done at the root (Case 3).   
  
**Examples of some standard algorithms whose time complexity can be evaluated using the Master Method** 

- [Merge Sort](http://geeksquiz.com/merge-sort/): T(n) = 2T(n/2) + Θ(n). It falls in case 2 as c is 1 and Logba] is also 1. So the solution is Θ(n Logn) 
- [Binary Search](http://geeksquiz.com/binary-search/): T(n) = T(n/2) + Θ(1). It also falls in case 2 as c is 0 and Logba is also 0. So the solution is Θ(Logn) 

**Notes:** 

- It is not necessary that a recurrence of the form T(n) = aT(n/b) + f(n) can be solved using Master Theorem. The given three cases have some gaps between them. For example, the recurrence T(n) = 2T(n/2) + n/Logn cannot be solved using master method. 
- Case 2 can be extended for f(n) = Θ(ncLogkn)   
    If f(n) = Θ(ncLogkn) for some constant k >= 0 and c = Logba, then T(n) = Θ(ncLogk+1n) 

### Space Complexity
The term Space Complexity is misused for Auxiliary Space at many places. Following are the correct definitions of Auxiliary Space and Space Complexity. 

_Auxiliary Space_ is the extra space or temporary space used by an algorithm.

_The space Complexity_ of an algorithm is the total space taken by the algorithm with respect to the input size. Space complexity includes both Auxiliary space and space used by input. 

For example, if we want to compare standard sorting algorithms on the basis of space, then Auxiliary Space would be a better criterion than Space Complexity. Merge Sort uses O(n) auxiliary space, Insertion sort, and Heap Sort use O(1) auxiliary space. The space complexity of all these sorting algorithms is O(n) though. 

Space complexity is a parallel concept to time complexity. If we need to create an array of size n, this will require O(n) space. If we create a two-dimensional array of size n*n, this will require O(n2) space.

In recursive calls stack space also counts. 

**Example :** 

Python

```python
def add(n):
  if(n<=0):
    return 0
  
  return n + add(n-1)

```

Here each call add a level to the stack :

1.  add(4)
2.    -> add(3)
3.      -> add(2)
4.        -> add(1)
5.          -> add(0)

Each of these calls is added to call stack and takes up actual memory.
So it takes O(n) space.

However, just because you have n calls total doesn’t mean it takes O(n) space.

Look at the below function :

Python

```python
def addSequence(n):
  sum=0
  for i in range(0,n):
    sum+=pairSum(i,i+1)
    
  return sum

def pairSum(x,y):
  return x+y

```

There will be roughly O(n) calls to pairSum. However, those calls do not exist simultaneously on the call stack, so you only need O(1) space.

**Note:** It’s necessary to mention that space complexity depends on a variety of things such as the programming language, the compiler, or even the machine running the algorithm.




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
