# Euclidean Distance
#wiki #cs4375 

A method to measure [[Similarity & Dissimilarity Measures|dissimilarity]] between two objects in $n$-dimensional space.

## Formula
$$d(\mathbf{x}, \mathbf{y}) = \sqrt{\sum_{k=1}^{n}{(x_k - y_k)^2}}$$

where $n$ is the number of dimensions/attributes and $x_k \text{ and } y_k$ are, respectively the $k^{th}$ attributes of data objects $x$ and $y$

If the scales differ, standardization is necessary.

## Properties
### Positivity
$$d(\mathbf{x},\mathbf{y})\geq 0,\: \forall \mathbf{x},\mathbf{y}$$
$$d(\mathbf{x},\mathbf{y}) = 0, \iff \mathbf{x}=\mathbf{y}$$

### Symmetry
$$d(\mathbf{x},\mathbf{y}) = d(\mathbf{y},\mathbf{x}),\: \forall \mathbf{x},\mathbf{y}$$

### Triangle inequality
$$d(\mathbf{x},\mathbf{z}) \leq d(\mathbf{x},\mathbf{y}) + d(\mathbf{y},\mathbf{z})$$
