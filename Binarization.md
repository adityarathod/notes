# Binarization
A [[Data Preprocessing|data preprocessing]] method that converts a discrete attribute to one or more binary attributes.

## Methods
There's one primary method to achieve binarization:

1. Assign each of the $m$ possible categorical values to an integer in the interval $[0, m-1]$. If the attribute is ordinal, then ensure the assignment maintains the order.
2. Convert each of these integers into the binary representation. Now you have $\lceil \log_{2}{m} \rceil$ binary attributes.
