# Modularity on the Karate Club Graph

**DSC212: Graph Theory Module, Research Assignment**

This project implements recursive spectral modularity partitioning from scratch on Zachary's Karate Club network (34 nodes, 78 edges), following Newman (2006).

## What the notebook does

1. Builds the adjacency matrix A, degree vector k and modularity matrix B = A − k kᵀ / 2m (edge weights ignored, so A ∈ {0,1}).
2. Splits a community using the sign of the leading eigenvector of its block B^(C), and stops when the leading eigenvalue is ≤ 0.
3. Applies the split recursively and saves a snapshot of the partition after each split.
4. Plots the graph at every iteration with a fixed spring layout, one color per community and node IDs as labels.
5. Computes degree, betweenness and closeness centrality and the clustering coefficient on each node's community subgraph after every split, stored in dictionaries keyed by iteration.
6. Plots how each metric evolves across iterations.
7. Compares the first split with the real club division and discusses the results.

## Results

- The recursion ends with **5 communities** after 4 splits.
- Modularity rises from Q = 0 (whole graph) to 0.3715 after the first split and 0.4094 at the end.
- The first bisection matches the real club split except for **node 8** (1 of 34 misclassified, accuracy 0.971).

## Files

| File | Description |
|---|---|
| `KarateClub.ipynb` | Main notebook with code, outputs, plots and discussion |
| `requirements.txt` | Python packages needed to run the notebook |
| `assets/` | Exported figures |

## Reference

Newman, M. E. J. (2006). Modularity and community structure in networks. *Proceedings of the National Academy of Sciences*, 103(23), 8577–8582.
