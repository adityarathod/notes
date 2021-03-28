# CLRS Chapter 3.1-3.2: Asymptotic notation and standard notations

- The order of growth of $T(n)$ gives us an idea of how efficient an algorithm is an gives us a way to compare the relative performance of different algorithms
- Since certain terms dominate the growth of a running time, it's often not worth it to find the *exact* running time but rather the *asymptotic* efficiency of algorithms

# Asymptotic Notation

- $T(n)$ is defined for a domain of natural numbers
- Asymptotic notation is primarily used to characterize running times, but can be used applied to other things (like space)
- Three types of asymptotic running times: $\Theta(n)$, $\Omega(n)$, $O(n)$

## $\Theta$-Notation

For a given function $g(n)$, $\Theta(g(n))$ defines the set of functions such that:

$$\Theta(g(n)) = \\
\{\, f(n):\: 0 \leq c_1 g(n) \leq f(n) \leq c_2 g(n) \text{ such that }  c_1 > 0, c_2 > 0, n > n_0 > 0. \,\}$$

Essentially, $g(n)$ is sandwiched between $c_1 g(n)$ and $c_2 g(n)$.

As such, $g(n)$ is an **asymptotically tight** bound for $f(n)$

## $O$-Notation

The $\Theta$ notation bounds a function from both sides. Big O specifically focuses on an **asymptotic upper bound.**

For a given function $g(n)$, $O(g(n))$ defines the set of functions such that:

$$O(g(n))= \\
\{\, f(n): \: \text{there exist } c > 0, n_0 > 0 \text{ such that } 0\leq f(n) \leq cg(n) \text{ for all } n \geq n_0
\,\}$$