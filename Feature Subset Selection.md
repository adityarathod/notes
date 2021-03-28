# Feature Subset Selection
#wiki #cs4375 

A [[Data Preprocessing|data preprocessing]] method that removes redundant and irrelevant features. The presence of such features affects classification accuracy and cluster quality.

## Methods
Each method has its own trade-offs.

### Common sense/Domain knowledge
Application of specialized or common knowledge to remove features that are known to be redundant.

### Embedded approaches
Features are selected naturally as part of the machine learning algorithm.

### Filter approaches
Features are selected before the machine learning algorithm is run. For example, we can select attributes that are lowest in terms of correlation.

Because we use a correlation-based approach, we can predict how well the algorithm will perform given a set of attributes.

### Wrapper approaches
Features are selected by using the machine learning algorithm as a black box to search for the best subset of attributes by measuring how well the algorithm performs on a given set of attributes.

### Feature weighting
Allows for combining domain knowledge or other information while retaining features by weighting the importance of a feature before it's used.