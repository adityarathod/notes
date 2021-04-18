# Data Density
#wiki #cs4375 

The **density** of the data measures the degree to which data are close together in a specified area.

This measure is used for **clustering** and **anomaly detection**.

## Euclidean density
A way to measure density as number of points per unit volume. Can be defined in two ways: **grid-based** and **center-based** approaches

### Grid-based approach
Divide the region into rectangular cells, count the number of points in each cell, define density as the number of points the cell contains

### Center-based approach
Use a point as a *center point* and count the number of cells within a specified radius of the point.
