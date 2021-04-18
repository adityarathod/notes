# Correlation Coefficient
#wiki #cs4375 #opre3360 

The correlation between two objects with binary or continuous attributes measures the linear relationship between the objects' attributes.

The **correlation coefficient** is defined as

$$
\text{corr}(\mathbf{x}, \mathbf{y}) = \frac{\text{cov}(\mathbf{x},\mathbf{y})}{\text{SD}(\mathbf{x})\cdot\text{SD}(\mathbf{y})}
$$

The closer $|\text{corr}(\mathbf{x}, \mathbf{y})|$ is to  1, the stronger the relationship. The sign indicates the direction of the relationship.

## Formulas for a sample
$$
\text{cov}(\mathbf{x}, \mathbf{y}) = s_{xy} = \frac{1}{n-1}\sum_{k=1}^{n}{(x_k - \bar{x})(y_k - \bar{y})}
$$

$$
\text{SD}(\mathbf{x}) = s_{x} = \sqrt{\frac{1}{n-1}\sum_{k=1}^{n}{(x_k - \bar{x})^2}}
$$

$$
\text{SD}(\mathbf{y}) = s_{y} = \sqrt{\frac{1}{n-1}\sum_{k=1}^{n}{(y_k - \bar{y})^2}}
$$

$\bar{x}$ and $\bar{y}$ are the means of $\mathbf{x}$ and $\mathbf{y}$, respectively.

## Formulas for a population
$$
\text{cov}(\mathbf{x}, \mathbf{y}) = s_{xy} = \frac{1}{n}\sum_{k=1}^{n}{(x_k - \bar{x})(y_k - \bar{y})}
$$

$$
\text{SD}(\mathbf{x}) = s_{x} = \sqrt{\frac{1}{n}\sum_{k=1}^{n}{(x_k - \bar{x})^2}}
$$

$$
\text{SD}(\mathbf{y}) = s_{y} = \sqrt{\frac{1}{n}\sum_{k=1}^{n}{(y_k - \bar{y})^2}}
$$
