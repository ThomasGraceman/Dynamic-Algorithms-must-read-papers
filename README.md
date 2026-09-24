# Must-read papers on Dynamic Algorithms

Dynamic Algorithms: All-Pairs Shortest Paths, Distance Oracles, and Planar Graphs.

Contributed by Thomas Graceman.

## Content

- [Distance Oracles and Approximate Shortest Paths](#distance-oracles-and-approximate-shortest-paths)
- [Fully-Dynamic All-Pairs Shortest Paths](#fully-dynamic-all-pairs-shortest-paths)
- [Shortest Paths in Planar Graphs](#shortest-paths-in-planar-graphs)

## [Distance Oracles and Approximate Shortest Paths](#content)

1.  **Approximate distance oracles.** Journal of the ACM 2005. [paper](https://doi.org/10.1145/1044731.1044732)

    *Mikkel Thorup, Uri Zwick.*

    Introduces distance oracles: a data structure answering any distance query in O(1) time with stretch 2k−1, using only O(kn^{1+1/k}) space — the foundation for much of the later work on approximate shortest paths.

2.  **Dynamic approximate all-pairs shortest paths in undirected graphs.** FOCS 2004. [paper](https://ieeexplore.ieee.org/document/1366270)

    *Liam Roditty, Uri Zwick.*

    First near-optimal dynamic algorithms for approximate all-pairs shortest paths: decremental and fully-dynamic algorithms with stretch guarantees obtained by dynamizing the Thorup–Zwick oracle.

## [Fully-Dynamic All-Pairs Shortest Paths](#content)

1.  **Worst-case update times for fully-dynamic all-pairs shortest paths.** STOC 2005. [paper](https://doi.org/10.1145/1060590.1060607)

    *Mikkel Thorup.*

    First fully-dynamic APSP algorithm with worst-case update time faster than recomputation from scratch (Õ(n^{2.75})), using a hierarchical graph decomposition.

2.  **Fully-dynamic all-pairs shortest paths: improved worst-case time and space bounds.** SODA 2020. [paper](https://arxiv.org/abs/2001.10801)

    *Maximilian Probst Gutenberg, Christian Wulff-Nilsen.*

    Breaks Thorup's long-standing worst-case update bound and gives the first exact fully-dynamic APSP data structures with truly subcubic update time and near-quadratic space simultaneously.

## [Shortest Paths in Planar Graphs](#content)

1.  **Planar graphs, negative weight edges, shortest paths, and near linear time.** Journal of Computer and System Sciences 2006. [paper](https://doi.org/10.1016/j.jcss.2005.05.007)

    *Jittat Fakcharoenphol, Satish Rao.*

    Near-linear time (O(n log^3 n)) algorithm for shortest paths in planar graphs with arbitrary edge weights, including negative weights — a major improvement over earlier n^{3/2}-time algorithms.

2.  **Multiple-source shortest paths in planar graphs.** SODA 2005. [paper](https://doi.org/10.5555/1070432.1070454)

    *Philip N. Klein.*

    Builds a data structure that answers distance queries from any vertex to boundary vertices of a planar graph in O(log n) time, by dynamically maintaining a shortest-path tree as the source slides along the boundary. A key building block for later planar algorithms.