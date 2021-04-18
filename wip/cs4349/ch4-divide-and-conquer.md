# Divide-and-Conquer Algorithms
- Mergesort is a divide-and-conquer algorithm
- Many other problems can be solved using this technique:
  - Maximum-subarray problem
  - Square matrix multiplication
  - Exponentiation

## Applications of Divide-and-Conquer
- **Maxiumum-subarray problem**: take an array of numbers and determine the contiguous subarray whose values have the greatest sum
  - Bruteforce: $O(n^2)$
  - Divide-and-conquer: $O(n \log n)$
- **Square matrix multiplication**: Multiply two square matrices
  - Naive solution w/ three nested loops: $O(n^3)$
  - Strassen's algorithm: $O(n^{2.81})$, beating the straightforward method asymptotically
- **Exponentiation**: Finding $a^b$ for arbitrary $a$ and $b$
  - Iterative: $O(n)$
  - Divide-and-conquer: $O(n)$

## Problem: Maximum-Subarray
