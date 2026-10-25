# Must-read papers on Dynamic Algorithms

Dynamic Algorithms

Contributed by Taha hoseinpour.

Feel free to ask questions or add any paper to the list.

The main focus here is on shortest path, maximum flow, ... problems in a dynamic setting, and more generally, dynamic graph problems.

## Content

- [Distance Oracles and Approximate Shortest Paths](#distance-oracles-and-approximate-shortest-paths)
- [Fully-Dynamic All-Pairs Shortest Paths](#fully-dynamic-all-pairs-shortest-paths)
- [Shortest Paths in Planar Graphs](#shortest-paths-in-planar-graphs)
- [Dynamic Cuts, Distances, and Effective Resistances](#dynamic-cuts-distances-and-effective-resistances)
- [Talks: design templates](#talks-design-templates)

## [Distance Oracles and Approximate Shortest Paths](#content)

1.  **Approximate distance oracles.** Journal of the ACM 2005. [paper](https://doi.org/10.1145/1044731.1044732)

    *Mikkel Thorup, Uri Zwick.*

    Introduces distance oracles: a data structure answering any distance query in O(1) time with stretch 2k−1, using only O(kn^{1+1/k}) space, and is the foundation for much of the later work on approximate shortest paths. Fundamentally, Thorup's underlying question was a question regarding the compactification of available data, using randomized sampling as a convenient tool.

2.  **Dynamic approximate all-pairs shortest paths in undirected graphs.** FOCS 2004. [paper](https://ieeexplore.ieee.org/document/1366270)

    *Liam Roditty, Uri Zwick.*

    First near-optimal dynamic algorithms for approximate all-pairs shortest paths: decremental and fully-dynamic algorithms with stretch guarantees obtained by dynamizing the Thorup–Zwick oracle. Their main insight, which can be used and has been used extensively, is to maintain a number of shallow data structures, here being the Even-Shiloach tree, to dynamically maintain the queries.

## [Fully-Dynamic All-Pairs Shortest Paths](#content)

1.  **Worst-case update times for fully-dynamic all-pairs shortest paths.** STOC 2005. [paper](https://doi.org/10.1145/1060590.1060607)

    *Mikkel Thorup.*

    First fully-dynamic APSP algorithm with worst-case update time faster than recomputation from scratch (Õ(n^{2.75})), using a hierarchical graph decomposition. The ideas and insights in these papers have been used extensively in later papers to obtain better worst-case times. If I am not mistaken, Saranurak has a talk on this method.

2.  **Fully-dynamic all-pairs shortest paths: improved worst-case time and space bounds.** SODA 2020. [paper](https://arxiv.org/abs/2001.10801)

    *Maximilian Probst Gutenberg, Christian Wulff-Nilsen.*

    Breaks Thorup's long-standing worst-case update bound and gives the first exact fully-dynamic APSP data structures with truly subcubic update time and near-quadratic space simultaneously.

## [Shortest Paths in Planar Graphs](#content)

1.  **Planar graphs, negative weight edges, shortest paths, and near linear time.** Journal of Computer and System Sciences 2006. [paper](https://doi.org/10.1016/j.jcss.2005.05.007)

    *Jittat Fakcharoenphol, Satish Rao.*

    Near-linear time (O(n log^3 n)) algorithm for shortest paths in planar graphs with arbitrary edge weights, including negative weights, a major improvement over earlier n^{3/2}-time algorithms. The main tool which allowed them to devise such an algorithm was the usage of planarity and the separation result in planar graphs. The separation allows them to design a data structure based on the divide-and-conquer method; there has been an extensive introduction on a course by Erik Demaine at MIT and another course on computational topology by Jeff Erickson, which you can read.

2.  **Multiple-source shortest paths in planar graphs.** SODA 2005. [paper](https://doi.org/10.5555/1070432.1070454)

    *Philip N. Klein.*

    Builds a data structure that answers distance queries from any vertex to boundary vertices of a planar graph in O(log n) time, by dynamically maintaining a shortest-path tree as the source slides along the boundary. A key building block for later planar algorithms.

## [Dynamic Cuts, Distances, and Effective Resistances](#content)

1.  **Fast dynamic cuts, distances and effective resistances via vertex sparsifiers.** FOCS 2021. [paper](https://arxiv.org/abs/2005.02368)

    *Li Chen, Gramoz Goranci, Monika Henzinger, Richard Peng, Thatchaphol Saranurak.*

    Explanation placeholder: Brief summary of the paper's significance, key contributions, and relevance to dynamic algorithms.

## [Talks: design templates](#content)

Thatchaphol Saranurak's tutorial on **design templates** for dynamic graph algorithms: reusable patterns for attacking many problems (vertex sparsifiers, black-box reductions to static primitives, and adversary models).

1. **Graph Data Structures, Part 1.** Simons Institute (Data Structures and Optimization for Fast Algorithms Boot Camp, 2023). [video](https://www.youtube.com/watch?v=6BV8yUVrbug&list=PLgKuh-lKre130uhdi7B-3yCZfIxSB4MNn&index=2&t=2920s)

    *Thatchaphol Saranurak.*

    Sets up the dynamic-graph model (preprocess, then online updates and queries) and the template viewpoint: how to turn static structure into a data structure that can be maintained under updates.

2. **Graph Data Structures, Part 2.** Simons Institute (Data Structures and Optimization for Fast Algorithms Boot Camp, 2023). [video](https://www.youtube.com/watch?v=rP-IU7NJKcI&list=PLgKuh-lKre130uhdi7B-3yCZfIxSB4MNn&index=4&t=2505s)

    *Thatchaphol Saranurak.*

    The vertex-sparsifier template, developed on min-max paths (MST + LCA closure of terminals). Shows how a sparsifier for a static problem becomes a black-box recipe for a dynamic algorithm.

3. **Graph Data Structures, Part 3.** Simons Institute (Data Structures and Optimization for Fast Algorithms Boot Camp, 2023). [video](https://www.youtube.com/watch?v=7pUbd4dpigM&list=PLVw32sKsg0NuBGS8rqsRFxKAq5pYhzd2K&index=22)

    *Thatchaphol Saranurak.*

    Templates against different adversaries (oblivious vs adaptive): which design patterns from the literature apply to each, and how the interaction model changes what you can assume about the update sequence.
