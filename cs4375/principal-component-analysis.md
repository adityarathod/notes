# Principal Component Analysis
#wiki #cs4375 

Principal component analysis, or PCA, is a linear algebra technique that finds new attributes based on the existing continuous attributes.

These new attributes follow certain constraints:
- are linear combinations of the original attributes
- are orthogonal to each other
- capture the maximum amount of variation in the data


## Performing PCA
1. Calculate averages for the variables you want to reduce to create a point in space which will be the center of the data.
2. Subtract the center from all points to center them at the origin.
3. Fit a line through the data that passes through the origin either by maximizing the distance from point projected onto line and the origin. This is also minimizing the distance from point to projected point. The distance is measured as the sum of squared distances from the point and the origin.
4. Find the slope of the line and divide by 3rd side of right triangle to get a unit vector in the direction of the line. This is the *eigenvector* for that principal component. To find the eigenvalue, square root the sum of squared distances. This will give you the eigenvector and eigenvalue of 1 principal component.
6. To find the others, we just find all lines perpendicular to this one in all dimensions. Find the eigenvalues and eigenvectors similarly.
7. To calculate the amount of variation each principal component accounts for, divide the sum of squared distances by the number of points - 1 ($SS/n-1$).
