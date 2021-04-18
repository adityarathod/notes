# Useful Math Formulas
#wiki #cs4349 

This is a listing of useful math facts and formulas for algorithmic analysis.

## Monotonicity
A given function $f(n)$ is:
- ***monotonically increasing*** if $a \leq b \implies f(a) \leq f(b)$
- ***monotonically decreasing*** if $a \leq b \implies f(a) \geq f(b)$
- ***strictly increasing*** if $a < b \implies f(a) < f(b)$
- ***strictly decreasing*** if $a < b \implies f(a) > f(b)$

## Floors and Ceilings
- **Floor** ($\lfloor x \rfloor$): greatest integer $\leq x$
- **Ceiling**: ($\lceil x \rceil$): smallest integer $\geq x$

## Logarithms
- $\log_b n$: base-$b$ log of $n$
- $\lg n = \log_2 n$: binary log of $n$
- $\ln n = \log_e n$: natural log of $n$

## Factorials
- $n! = \begin{cases} 1 & \text{if } n = 0,\\ n \cdot (n-1)! & \text{if } n > 0\end{cases}$
- $n! = 1 \times 2 \times 3 \times \text{...} \times n$
- $n! \leq n^n$, thus, $O(n^n)$
- Sterling's approximation: $n! = \sqrt{2 \cdot \pi \cdot n} \left(\frac{n}{e}\right)^n \left( 1 + \Theta(1/n) \right)$

## Ranking of Functions
$O(1) \leq O(\lg n) \leq O(n) \leq O(n \lg n) \leq O(n^2) \leq O(n^3) \leq O(n^k) \leq O(2^n)$

## Summations
### Arithmetic Series
$$\sum_{k=1}^{n}{k} = 1+2+\text{...}+n = \frac{n(n+1)}{2}$$

### Geometric Series
$$\sum_{k=0}^{n}{x^k} = \frac{x^{n+1} - 1}{x-1} \:\: (x \neq 1)$$

$$\sum_{k=0}^{n - 1}{x^k} = \frac{x^n - 1}{x-1} \:\: (x \neq 1)$$

### Special Geometric Series
$$\sum_{k=0}^{n-1}{2^k} = 2^n-1$$

$$\sum_{k=0}^{\infty}{x^k} = \frac{1}{1-x} \:\: (x < 1)$$

### Harmonic Series
$$\sum_{k=1}^{n}{\frac{1}{k}} = \frac{1}{1} + \frac{1}{2} + \text{...} + \frac{1}{n} \approx \ln n$$
