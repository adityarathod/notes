---
layout: math
---

# Recurrences
#wiki #cs4349 

**Recurrences** are equations or inequalities that describe a function in terms of its value on smaller inputs. In algorithmic analysis, they are a good way to recursively express running time.

Example:

$$
T(n) = \begin{cases}
\Theta(1) & \text{if } n = 1, \\
2T(n/2) + \Theta(n) & \text{if } n > 1.
\end{cases}
$$


## Recurrences and Recursion
The running time of recursive functions can be expressed as recurrences trivially. Here are some illustrative examples:

- Example: $T(n) = 2 T(n/2) + n$
  - We solve 2 subproblems of size $n/2$
  - We do $n$ units of additional work
- Another example: $T(n) = 3 T(n-1) + n$
  - We solve 3 subproblems of size $n-1$
  - We do $n$ units of additional work

## Solving Recurrences
**Solving** a recurrence means finding a non-recursive formula for it. There are three primary methods for solving recurrences:

- **Substitution method** = guess a bound and prove it using induction
- **Recursion tree method** = convert recurrence into tree of costs
- **Master method** = provides bounds of recurrences in the form $T(n) = a T(n/b) + f(n)$ where $a \geq 1$, $b > 1$, and $f(n)$ is some function

### Substitution Method
In this method, we guess the form of the solution (or are usually given it), and we use induction to prove the guess is correct as well as find any necessary constants.

It is called *substitution* because we "substitute" the guessed solution for the function when applying the inductive hypothesis to smaller values.

### Recursion Tree Method
In this method, we draw a tree with levels, where each level is a recursion level and contains the following parts:

1. The problem size
2. The recursion tree
3. The total work done

### Master Method
Depends on the Master Theorem:

> **Master Theorem**
> Let $a \geq 1$ and $b>1$ be constants, let $f(n)$ be a function, and let $T(n)$ be defined on the positive integers by the recurrence
> $$T(n) = a T(n/b) + f(n),$$
> where we interpret $n/b$ to be $\lfloor n/b \rfloor$ or $\lceil n/b \rceil$. Then, $T(n)$ has the following asymptomatic bounds:
> 1. If $f(n) = O(n^{\log_b{a} - \epsilon})$ for some $\epsilon > 0$, then $T(n)=\Theta(n^{\log_b a})$.
> 2. If $f(n) = \Theta(n^{\log_b a})$, then $T(n) = \Theta(n^{\log_b a} \lg n)$.
> 3. If $f(n) = \Omega(n^{\log_b a + \epsilon})$ for some $\epsilon > 0$, and if $a f(n/b) \leq c f(n)$ for some constant $c < 1$ and all sufficiently large $n$, then $T(n) = \Theta(f(n))$.

To use this method, simply apply the Theorem.
