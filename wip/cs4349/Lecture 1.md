# Lecture 1
#lecture #cs4349 

Date: 1/20/21

- This class will be useful for problem solving and interviews
    - However, it does not seem like a big coding class
- About the prof: originally Turkish

# Intro to the Course Slides
- Recurrences: Recursive algorithms mapped to a runtime complexity via a recurrence relation
    - Example: $T(n) = 2n+1$
- Greedy algorithms: At every step, looks at the best option without doing further analysis
- Dynamic programming: Solve problem by solving subproblems and storing those subproblem solutions
- Textbook: *Introduction to Algorithms* (also called CLRS)
    - This is a comprehensive book used by undergrads, grad students, and postgrads—as such, this course will cover a subset of the text
- No late work is accepted

# Lecture 1

## Algorithms

**Algorithm**
a well-defined computational procedure that takes some value(s) as input and produces some value(s) as output

**Data structure**
a way to store and organize data to allow for access/modification

**Instance of a problem**
the input needed to compute a solution to a problem

## Types of Problems Solved by Algorithms

- Analyzing, storing, and retrieving human DNA
- Finding good routes for data transfer for the internet (packet routing)
- Secure e-commerce using PKI and digital signatures
- Linear programming to reduce resources used

## The Sorting Problem

- **Input**: a sequence of n numbers $\langle a_1,a_2,...,a_n \rangle$
- **Output**: a permutation of the input such that $\langle a_{i1} \leq ... \leq a_{in} \rangle$
- When programming this, the input is an array
- There are many solutions to this problem: Insertion sort, merge sort, etc.

## Algorithm Efficiency

- How do we compare efficiency of algorithms if, say, Computer A is faster than Computer B but are running different algorithms?
- Let's compare insertion sort and merge sort:
    - Insertion sort: $T(n)=c_1 n^2$
    - Merge sort: $T(n) = c_2 n \log n$
- For sufficiently large *n* (even on computers of extremely varying speed), insertion sort will prove to be slower due to the nature of the growth of its runtime complexity ($O(n^2)$  vs $O(n \log n)$)

## Insertion Sort

- Is of order $n \log n$ because we split up the array into two recursively and sort the split array recursively
- Called an **in place algorithm** because numbers are rearranged within the array

**In-place algorithm**
An algorithm that modifies its input while only allocating constant extra space.

- Pseudocode for insertion sort:

```
InsertionSort(A)
	for j = 2 to length(A)
		key = A[j]
		i = j - 1
		while i > 0 and A[i] > key
			A[i+1] = A[i]
			i = i - 1
		A[i+1] = key
```

To be continued on Monday