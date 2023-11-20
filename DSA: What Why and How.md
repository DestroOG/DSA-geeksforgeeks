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

