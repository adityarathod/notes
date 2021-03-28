# Binary Vector Similarity
#wiki #cs4375

Binary vector similarity is measured via **similarity coefficients**.

A similarity coefficient value of 1 means the two vectors are identical, while a value of 0 means the vectors are not at all similar.

## Important values
We can use the following values to calculate similarities between two vectors $p$ and $q$:

- $f_{01}$ = the number of attributes where the value in $p$ was 0 and $q$ was 1
- $f_{10}$ = the number of attributes where the value in $p$ was 1 and $q$ was 0
- $f_{00}$ = the number of attributes where the value in $p$ was 0 and $q$ was 0
- $f_{11}$ = the number of attributes where the value in $p$ was 1 and $q$ was 1

## Types of similarity
### Simple matching
$$s=\frac{\text{\# matches}}{\text{\# attributes}} = \frac{f_{11} + f_{00}}{f_{01} + f_{00} + f_{10} + f_{11}}$$

### Jaccard coefficients
$$
s = \frac{\text{\# 11 matches}}{\text{\# non-zero attributes}}
= \frac{f_{11}}{f_{01} + f_{10} + f_{11}}
$$
