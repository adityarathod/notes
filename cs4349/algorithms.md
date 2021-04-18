---
layout: math
---

# Algorithms
#wiki #cs4349 

An **algorithm** is a well-defined computational procedure that takes some input and produces output.

In essence, algorithms take some data as input (the **instance** of the problem, stored in a **data structure**) and produce the solution as output.

## Types of Solvable Problems
Algorithms cover a wide array of problems and domains, whether it's analyzing DNA, allocating resources in an organization, efficiently transferring data, or securing transactions.

## Algorithmic Efficiency
While there may be many different algorithms to solve a problem, how do we determine which one is the _most efficient?_ Since we cannot rely on the speed of the computer running it (which can vary), we use the **rate of growth** of the running time as the input grows or changes.

## Describing Algorithms
Good algorithm descriptions consist of 3 parts:

1. The algorithm, expressed in clear and concise terms (can be pseudocode)
2. A proof that the algorithm is correct
3. The running time of the algorithm and a derivation

## Designing Algorithms
When designing algorithms to solve novel problems, there are some best practices to follow:

- Incremental design: solve the problem iteratively rather than all at once.
- Divide and conquer: recursively call yourself on increasingly small subproblems.
  - *Divide* into smaller subproblems.
  - *Conquer* subproblems by solving them recursively.
  - *Combine* subproblem solutions.

## Divide-and-Conquer Algorithm Example: Merge Sort
- Utilizes divide-and-conquer in this way:
  - *Divide* the n-element sequence into two subsequences of size $n/2$ each 
  - *Conquer* each subproblem by sorting the two sequences recursively using merge sort
  - *Combine* each subproblem by merging the two sorted subsequences to produce the sorted solution (merge 2 sorted arrays)

### Pseudocode

```
MergeSort(A, p, r)
  if p < r then
    q = floor((p+r) / 2)
    MergeSort(A, p, q)    # sorts first half of array recursively
    MergeSort(A, q+1, r)  # sorts second half of array recursively
    Merge(A, p, q, r)     # merge the two sorted arrays in linear time
```

### Proof
Drawing the recursion tree is useful.

### Running Time Analysis
#### Finding Running Times of Divide-and-Conquer Algorithms
To analyze a divide-and-conquer algorithm, we must first find the running time:
- If the problem size is smaller than some constant c, it's just $\Theta(1)$
- If division of the problem yields $a$ subproblems each of size $1/b$, the, then it takes $a T(n/b)$ time to solve all of those subproblems. Assuming that we take $D(n)$ time to divide the problem and $C(n)$ to combine the solutions, the generalized recurrence is:

$$
T(n) = \begin{cases}
\Theta(1) & \text{if } n \leq c,\\
aT(n/b) + D(n) + C(n) & \text{otherwise}.
\end{cases}
$$

As such, we can find the running time of Merge Sort by solving this recurrence:

$$
T(n) = \begin{cases}
\Theta(1) & \text{if } n =1,\\
2T(n/2) + + C(n) & \text{if } n > 1.
\end{cases}
$$

Using a recursion tree, we note that the tree has $\log n + 1$ levels, each costing $cn$, making the total cost $cn(\log n + 1) = cn \log n + cn$. Ignoring constants and low-order terms, we get $\Theta (n \log n)$ for the running time complexity of this algorithm.

