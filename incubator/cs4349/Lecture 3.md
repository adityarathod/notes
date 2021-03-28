# Lecture 3
#lecture #cs4349 

Date: 1/27/21

# Running Time

## Theta Notation

- $\Theta(g(n))=f(n)$ iff there exist positive constants c_1, c_2, and n_0 s.t. 0 \leq c_1 g(n) \leq f(n) \leq c_2 g(n) for all n > n_0
- $\Theta (g(n))$ is a set of functions
- $f(n) = \Theta(g(n))$ really means that f(n) belongs to $\Theta(g(n))$
- g(n) is called an *asymptotically tight bound* for f(n)

![](l3-bound-1.png)

Theta notation bounds a function within constant factors.

## O Notation

- $f(n)=O(g(n))$ means g(n) is an asymptotic upper bound for f(n)
- $O(g(n))=f(n)$ iff there exist positive constants c and n_0 s.t. 0 \leq f(n) \leq c g(n) for all n \geq n_0
- $f(n)= \Theta(g(n)) \implies f(n) =O(g(n))$, but $f(n)= \Theta(g(n)) \text{is not implied by} f(n) =O(g(n))$

![](l3-bound-2.png)

## Omega Notation

- $f(n)=\Omega(g(n))$ means g(n) is an asymptotic lower bound for f(n)
- $\Omega(g(n))=f(n)$ iff there exist positive constants c and n_0 s.t. 0 \leq c g(n) \leq f(n) for all n \geq n_0
- $f(n)= \Theta(g(n)) \implies f(n) =\Omega(g(n))$, but $f(n)= \Theta(g(n)) \text{is not implied by} f(n) =\Omega(g(n))$
- Useful to discuss the best case running time of an algorithm

# Recurrences

- Are equations or inequalities that describe a function in terms of its value on smaller inputs

## What does recursion really mean?

- $T(n) = 2 T(n/2)+n$
    - Solve a problem of size $n$ by solving 2 subproblems of size $n/2$ and do $n$ units of additional work
- $T(n)=T(n/4)+n^2$
    - Solve a problem of size $n$ by solving 1 subproblem of size $n/4$ and do $n^2$ units of additional work
- $T(n)=3T(n-1)+1$
    - Solve a problem of size $n$, we must solve 3 subproblems of size $n-1$ and do $n$ units of additional work

## Methods to solve recurrences

- Substitution method: guess a bound and use mathematical induction to prove our guess
- Recursion-tree method: convert recurrence into a tree with nodes representing cost
- Master method: provides bounds fo recurrences of the form $T(n)=aT(n/b)+f(n)$ where a ≥ 1, b > 1, and f(n) is a given function

### Substitution method

- Guess the form of solution, use induction to prove guess and find constants
- We substitute the guessed solution for the function when applying the inductive hypothesis, thus the name

**Example 1**
Prove that $T(n)=3T(n/3)+n=O(n\log n)$

**Solution 1**
Need to show that $T(n)\leq c n \log n$, for some c and some sufficiently large n

Assume this is true for $T(n/3)$: 
$T(n/3) \leq cn/3 \log (n/3)$
Let c = 3:
$T(n) = 3 T(n/3) +n \leq 3\;cn/3 \log (n/3)+n$

Example 2
Prove that $T(n)=3T(n/4)+n^2 = O(n^2)$

Solution 2

Need to show that $T(n) \leq cn^2$

Assume that the recurrence relation is true for $T(n/4)$.

As such, $T(n/4)\leq c(n/4)^2 = \frac{cn^2}{16}$

Using this, $T(n) = 3T(n/4)+n^2 \leq 3 \frac{cn^2}{16} + n^2$

Simplifying,  $T(n) = 3T(n/4)+n^2 \leq (\frac{3c}{16} + 1)n^2 \leq cn^2$

Looking at the right two inequalities: $(3c/16 + 1) \leq c \implies 1 \leq 13c/16$

### Recursion Tree Method

- Draw a recursion tree in levels—each level represents a level and has 3 parts:
    - Problem size
    - Recursion tree
    - Total work done
-