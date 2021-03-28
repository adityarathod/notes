# Sampling Methods
#wiki #cs4375 #opre3360 

A form of [[Data Preprocessing|data preprocessing]] where a subset of the data is selected for analysis. An effective sample (defined below) will work just as well for the task as the entire dataset.

A **representative sample** is a sample that has approximately the same property of interest as the original dataset.

There are two types of sampling: *random sampling* and *stratified sampling*

## Types of sampling
### Random sampling
Selecting items randomly has an equal opportunity of selecting any particular item.

There are two types of random sampling: **with replacement** and **without replacement**.

In random sampling with replacement, the object is not removed from the selection pool once selected, leaving a chance to select the same object multiple times. In sampling without replacement, this is not possible, as picked objects are removed from the population.

While each object has an equal probability of being selected, random sampling breaks down when we have a bunch of types of objects and different numbers of each type, since a random sample may fail to adequately represent less-frequent objects.

### Stratified sampling
Stratified sampling solves this problem. Equal numbers of objects from each group are selected, despite being each group being of different sizes.

Another variation of stratified sampling has the numbers of objects be proportional to the size of the group.

## Sample size
While larger sample sizes increase the chance a sample will be representative, if a sample becomes too large it eliminates the point of sampling.

If sample sizes are too small, patterns may be missed or incorrect patterns may be inferred.
