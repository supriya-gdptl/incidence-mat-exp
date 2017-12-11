# INCIDENCE-MATRIX-EXPERIMENT
Study properties of incidence matrix of the graph

# CONCLUSION
### Learned node/edge features are highly dependent on which matrix factorization method is used

*1) Non-negative matrix factorization(NMF):*

  - (why to use this:)Decomposes matrix X = W^T.H using alternating minimization algorithm. We can use Inductive matrix completion technique [Natarajan and Dhillon 2014](https://academic.oup.com/bioinformatics/article/30/12/i60/385272) to incorporate extra infor(like node features and edge features) while decomposing.
    
  - (disadv:)Works only on matrix with non-negative entries.
*2) Singular value decomposition(SVD):*

  - (Why use this:)popular method. Decomposes matrix into 3 matrices.
    
  - (disadv:) Is it possible add extra infor while decomposing(something similar to NMF)
    
## OBSERVATION:

### Incidence matrix gives good separable node features as well as edge features

  - NMF is allowed on Incidence matrix.
    
  - Decomposed W matrix contains features of rows of incidence matrix which are nothing but the nodes of graph.
    
  - Scatter plot of both decompositions NMF and SVD, are nicely separable. However, representations of SVD are better.(This may be because, number of components used in NMF is 2, which leads to very high reconstruction error. perhaps, increasing it may help get better featuresusing NMF.)
    
  - ADV: along with good features, we are getting features for edges as well (which indicate reationship between nodes).
  - As NMF can be applied, we can make use of extra information while decomposition as per Inductive matrix completion [Natarajan and Dhillon 2014](https://academic.oup.com/bioinformatics/article/30/12/i60/385272)

    
### Normalized Graph Laplacian does not give good features for nodes

  - NMF does not work for this matrix
    
  - SVD works but does not give good features. Even after doing PCA and TSNE, the node features are not forming clusters according to communitites.
    
  - We get only node features.

### Adjacency matrix gives only good node features

  - NMF is allowed and gives good result but SVD gives better representation.
    
  - Gives only node features.
