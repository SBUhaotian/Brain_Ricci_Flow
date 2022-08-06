# Brain_Ricci_Flow

This work compute the Ollivier-Ricci Curvature[Ni], Ollivier-Ricci Flow[Ni2,Ni3], and Ricci community[Ni3] detected by Ollivier-Ricci flow metric.

In [Ni], edge Ricci curvature is observed to play an important role in the graph structure. An edge with positive curvature represents an edge within a cluster, while a negatively curved edge tent to be a bridge within clusters. Also, negatively curved edges are highly related to graph connectivity, with negatively curved edges removed from a connected graph, the graph soon become disconnected.

Ricci flow is a process to uniformized the edge Ricci curvature of the graph. For a given graph, the Ricci flow gives a "Ricci flow metric" on each edge as edge weights, such that under these edge weights, the Ricci curvature of the graph is mostly equal everywhere. In [Ni3], this "Ricci flow metric" is shown to be able to detect communities.

Both Ricci curvature and Ricci flow metric can act as a graph fingerprint for graph classification. The different graph gives different edge Ricci curvature distributions and different Ricci flow metric.

## Our Improvement
In our work, we are trying to detect Ricci community[Ni3] by Ollivier-Ricci flow metric for brain networks and other random generated graphs. These graphs are sparse graphs, e.g., there are 1,088 nodes and ~50,000 edges in a graph. At the same time, the community structure is not strong. It is not good for our Ricci flow metric to detect the communities using the predefined threshold.

Therefore, we add a greedy part in the code. In each round, we compute the Ricci metric. Then we remove the edge one by one, ordered by their weight. When one edge is removed, we compute the modularity of the current graph and maintain the one with the largest modularity. In each round, there are at most 60% edges are removed. Until the modularity cannot be increased, we obtain the final results.

## Getting Started
- Check the GraphRicciCurvature Python library (https://github.com/saibalmars/GraphRicciCurvature).
- You can run it with your graph Gpickle file using Automatical_Ricci_Flow.ipynb.
- You can also use Random_Network_Generator.ipynb to generate the random graph, with Stochastic Block Model (SBM) and Lancichinetti–Fortunato–Radicchi (LFR).

## Reference

[Ni]: Ni, C.-C., Lin, Y.-Y., Gao, J., Gu, X., and Saucan, E. "Ricci curvature of the Internet topology" (Vol. 26, pp. 2758–2766). Presented at the 2015 IEEE Conference on Computer Communications (INFOCOM), IEEE. [arXiv](https://arxiv.org/abs/1501.04138)

[Ni2]: Ni, C.-C., Lin, Y.-Y., Gao, J., and Gu, X. "Network Alignment by Discrete Ollivier-Ricci Flow", Graph Drawing 2018, [arXiv](https://arxiv.org/abs/1809.00320)

[Ni3]: Ni, C.-C., Lin, Y.-Y., Luo, F. and Gao, J. "Community Detection on Networks with Ricci Flow", Scientific Reports 9, 9984 (2019), [arXiv](https://arxiv.org/abs/1907.03993)
