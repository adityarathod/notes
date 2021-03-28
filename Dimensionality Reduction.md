# Dimensionality Reduction
#wiki #cs4375 

Datasets can have a large number of [[Attributes|attributes]], or features.

This technique has a few benefits:
- ML algorithms work better due to lower noise and no irrelevant features
- Can lead to a more understandable model
- Can be visualized better
- Time/memory required to process the data is reduced


## The curse of dimensionality
When the number of dimensions increases, the data becomes increasingly sparse in the space it occupies. Intuitively, this should make sense as more dimensions = more space to place data.

Density measurements (useful for clustering and outlier detection) become less useful as the points become more sparse. Thus, we need a means to solve this problem without losing the variation in the data.

## Principal component analysis (PCA)
One way to reduce the dimensionality of the data is **principal component analysis (PCA)**. It's discussed [[Principal Component Analysis|here]].
