# CLRS Chapter 2: Getting Started

- This chapter is all about understanding how to think about and analyze algorithms

# Insertion sort

- Let's go back to the **sorting problem**:

**The Sorting Problem**
*Input:* A sequence of $n$ numbers $\langle a_1, a_2, \dots,a_n\rangle$.
*Output:* A permutation of the input sequence $\langle a_1', a_2',\dots ,a_n'\rangle$ such that $a_1' \leq a_2' \leq \cdots\leq a_n'$.

- Insertion sort is a solution to the sorting problem that works a bit like how people sort a hand of playing cards, by taking one card at a time and putting it at the right place within the hand
- Pseudocode for insertion sort:

```
InsertionSort(A)
	for j = 2 to A.length
		key = A[j]
		i = j -1 
		while i > 0 and A[i] > key
			A[i+1] = A[i]
			i -= 1
		A[i+1] = key
```

- At each step, all the numbers in A from index 1 to i - 1 are sorted
    - This is called a *loop invariant*

# Analyzing algorithms

- *Analyzing* an algorithm means you must predict the resources that the algorithm requires
- In order to do so, we must simplify a model of a computer to something called the *random-access machine* (RAM) model
- In the RAM model:
    - Instructions executed one after the other
    - No concurrent operations
    - Each operation takes a fixed constant amount of time
- Even in the RAM model, analyzing algorithms requires combinatorics, probability theory, algebra, and asymptotic analysis

## Analyzing insertion sort

- How to define input size depends on the problem — in this case it's the size of A
- The running time is the number of primitive operations executed

### Step 1: Determine the cost of each line

If the cost is constant, assign it a unique constant

```
InsertionSort(A)                          --Cost--
	for j = 2 to A.length                      c1
		key = A[j]                               c2
		i = j - 1                                c4 
		while i > 0 and A[i] > key               c5
			A[i+1] = A[i]                          c6
			i -= 1                                 c7
		A[i+1] = key                             c8 
			
```

### Step 2: Determine how many times each line is run in relation to the input

This may require summations.

```
InsertionSort(A)                          --Cost--    --Times--
	for j = 2 to A.length                      c1           n
		key = A[j]                               c2         n - 1
		i = j - 1                                c4         n - 1 
		while i > 0 and A[i] > key               c5    sum(j=2 to n, tj)
			A[i+1] = A[i]                          c6    sum(j=2 to n, tj - 1)
			i -= 1                                 c7    sum(j=2 to n, tj - 1)
		A[i+1] = key                             c8         n - 1
```

### Step 3: Multiply each line's cost with the times it's run

$$T(n)= c_1 n + c_2 (n-1) + c_4(n-1) + c_5 \sum_{j=2}^{n}{t_j} +\\c_6 \sum_{j=2}^{n}{\left( t_j - 1 \right)} + c_7 \sum_{j=2}^{n}{\left(t_j-1\right)} + c_8(n-1)$$

Using summation formula:

$$T(n)= c_1 n + c_2 (n-1) + c_4(n-1) + c_5 \left( \frac{n(n+1)}{2} -1 \right) +c_6 \frac{n(n-1)}{2} + c_7 \frac{n(n-1)}{2} + c_8(n-1)
\\=\left(\frac{c_5 + c_6 + c_7}{2}\right) n^2 + (c_1+c_2+c_4+\frac{c_5}{2}-\frac{c_6}{2}-\frac{c_7}{2}+c_8)n \\- (c_2 + c_4 + c_5 +c_8)$$

## Worst-case and average-case analysis

- Typically you focus on the worst-case running time of an algorithm
- In some cases, you do care about the average-case running time

## Order of growth

- When analyzing algorithms, we care less about the actual running time (as we determined above), but rather the order of growth of the running time
- When we do this, we look at the leading term that contributes to the growth of the running time
    - For example, an average case of insertion sort is $\Theta(n^2)$

# Designing algorithms

- There are many ways to design algorithms—insertion sort is an *incremental* approach
- A second approach to explore is *divide-and-conquer*

### The divide-and-conquer approach

- A divide-and-conquer (DAC) approach is recursive and is requires three parts:
    - **Divide** the problem into subproblems which are smaller instances of the same problem
    - **Conquer** the subproblems by solving them recursively—or use the base case to solve in a straightforward manner
    - **Combine** the solutions to the subproblems into the complete solution
- A DAC approach to sort (called merge sort) is as follows:
    - **Divide**: Split the *n*-element subsequence into two subsequences of size *n/2*
    - **Conquer**: Sort the two subsequences via merge sort recursively (recursion base case: length 1 array)
    - **Combine**: Merge the two sorted subsequences using a two-pointer approach
- We can analyze DAC algorithms by using a recurrence equation, also called a *recurrence*, which describes the overall running time on a problem of size *n*  in terms of the running time on smaller inputs
- The generalized recurrence for a DAC algorithm that splits an input of size *n* into *a* subproblems of size *b*, takes $D(n)$ time to divide the problem, and $C(n)$ to combine the problem is:

$$T(n) = \begin{cases}
\Theta(1) & \text{if } n \leq c,\\
aT(n/b) + D(n) + C(n) & \text{otherwise.}
\end{cases}$$

- Next up: how to solve recurrences