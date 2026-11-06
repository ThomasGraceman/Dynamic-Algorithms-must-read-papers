# Must-read papers on Dynamic Algorithms

Dynamic Algorithms

Contributed by Taha hoseinpour.

Feel free to ask questions or add any paper to the list.

The main focus here is on shortest path, maximum flow, ... problems in a dynamic setting, and more generally, dynamic graph problems.

## Content

- [Distance Oracles and Approximate Shortest Paths](#distance-oracles-and-approximate-shortest-paths)
- [Compact Routing Schemes](#compact-routing-schemes)
- [Dynamic Trees](#dynamic-trees)
- [Fully-Dynamic All-Pairs Shortest Paths](#fully-dynamic-all-pairs-shortest-paths)
- [Shortest Paths in Planar Graphs](#shortest-paths-in-planar-graphs)
- [Dynamic Cuts, Distances, and Effective Resistances](#dynamic-cuts-distances-and-effective-resistances)
- [Maximum Flow](#maximum-flow)
- [Talks: design templates](#talks-design-templates)
- [Talks: continuous methods](#talks-continuous-methods)

## Distance Oracles and Approximate Shortest Paths

1.  **Approximate distance oracles.** Journal of the ACM 2005. [paper](https://doi.org/10.1145/1044731.1044732)

    *Mikkel Thorup, Uri Zwick.*

    Introduces distance oracles: a data structure answering any distance query in O(1) time with stretch 2k−1, using only O(kn^{1+1/k}) space, and is the foundation for much of the later work on approximate shortest paths. Fundamentally, Thorup's underlying question was a question regarding the compactification of available data, using randomized sampling as a convenient tool.

2.  **Dynamic approximate all-pairs shortest paths in undirected graphs.** FOCS 2004. [paper](https://ieeexplore.ieee.org/document/1366270)

    *Liam Roditty, Uri Zwick.*

    First near-optimal dynamic algorithms for approximate all-pairs shortest paths: decremental and fully-dynamic algorithms with stretch guarantees obtained by dynamizing the Thorup–Zwick oracle. Their main insight, which can be used and has been used extensively, is to maintain a number of shallow data structures, here being the Even-Shiloach tree, to dynamically maintain the queries.

## Compact Routing Schemes

1.  **Compact routing schemes.** SPAA 2001. [paper](https://doi.org/10.1145/378580.378581)

    *Mikkel Thorup, Uri Zwick.*

    Presents compact routing schemes for general weighted undirected networks that trade routing-table size against stretch, and introduces the landmark-based hierarchy that also underpins the Thorup–Zwick distance oracles.

## Dynamic Trees

1.  **A data structure for dynamic trees.** STOC 1981. [paper](https://doi.org/10.1145/800076.802464)

    *Daniel D. Sleator, Robert Endre Tarjan.*

    Introduces link-cut trees and the splay-tree machinery behind them, supporting link, cut, and path operations on dynamic trees in O(log n) amortized time. A foundational data structure for dynamic graph algorithms.

## Fully-Dynamic All-Pairs Shortest Paths

1.  **A new approach to dynamic all pairs shortest paths.** Journal of the ACM 2004. [paper](https://doi.org/10.1145/1039488.1039492)

    *Camil Demetrescu, Giuseppe F. Italiano.*

    Gives a fully-dynamic APSP algorithm for directed graphs with non-negative real-valued edge weights, supporting updates in O(n^2 log^3 n) amortized time and distance queries in O(1) worst-case time. This substantially improved previous bounds and solved a long-standing open problem.

2.  **Worst-case update times for fully-dynamic all-pairs shortest paths.** STOC 2005. [paper](https://doi.org/10.1145/1060590.1060607)

    *Mikkel Thorup.*

    First fully-dynamic APSP algorithm with worst-case update time faster than recomputation from scratch (Õ(n^{2.75})), using a hierarchical graph decomposition. The ideas and insights in these papers have been used extensively in later papers to obtain better worst-case times. If I am not mistaken, Saranurak has a talk on this method.

3.  **Fully-dynamic all-pairs shortest paths: improved worst-case time and space bounds.** SODA 2020. [paper](https://arxiv.org/abs/2001.10801)

    *Maximilian Probst Gutenberg, Christian Wulff-Nilsen.*

    Breaks Thorup's long-standing worst-case update bound and gives the first exact fully-dynamic APSP data structures with truly subcubic update time and near-quadratic space simultaneously.

## Shortest Paths in Planar Graphs

1.  **Planar graphs, negative weight edges, shortest paths, and near linear time.** Journal of Computer and System Sciences 2006. [paper](https://doi.org/10.1016/j.jcss.2005.05.007)

    *Jittat Fakcharoenphol, Satish Rao.*

    Near-linear time (O(n log^3 n)) algorithm for shortest paths in planar graphs with arbitrary edge weights, including negative weights, a major improvement over earlier n^{3/2}-time algorithms. The main tool which allowed them to devise such an algorithm was the usage of planarity and the separation result in planar graphs. The separation allows them to design a data structure based on the divide-and-conquer method; there has been an extensive introduction on a course by Erik Demaine at MIT and another course on computational topology by Jeff Erickson, which you can read.

2.  **Multiple-source shortest paths in planar graphs.** SODA 2005. [paper](https://doi.org/10.5555/1070432.1070454)

    *Philip N. Klein.*

    Builds a data structure that answers distance queries from any vertex to boundary vertices of a planar graph in O(log n) time, by dynamically maintaining a shortest-path tree as the source slides along the boundary. A key building block for later planar algorithms.

## Dynamic Cuts, Distances, and Effective Resistances

1.  **Fast dynamic cuts, distances and effective resistances via vertex sparsifiers.** FOCS 2020. [paper](https://arxiv.org/abs/2005.02368)

    *Li Chen, Gramoz Goranci, Monika Henzinger, Richard Peng, Thatchaphol Saranurak.*

    Introduces a general meta-theorem that turns any graph problem admitting a notion of *vertex sparsifier* into a dynamic data structure with sublinear update and query time. The new object is the *incremental vertex sparsifier*, measured by its *recourse* — how many edges change when a terminal is added — and stacking these into a hierarchy of depth ℓ costs an α^ℓ approximation factor, so a query is answered by running a static algorithm on the sparsest level. Instantiating the framework needs three ingredients: Madry's j-trees (built on Racke's oblivious routing) for cut-flow, a metric variant of them for distances that reinterprets Thorup–Zwick's distance oracle as a sparsifier, and random-walk based spectral vertex sparsifiers (Schur complements) for effective resistance. The payoff is fully dynamic all-pair max-flow/min-cut with O(log n log log n)-approximation in Õ(n^{2/3+o(1)}) amortized time against an oblivious adversary (Õ(m^{3/4}) against an adaptive one), fully dynamic approximate APSP and transshipment in Õ(n^{2/3+o(1)}) amortized time, and (1+ε)-approximate all-pair effective resistance in Õ(n^{2/3+o(1)}ε^{-O(1)}) amortized time, improving on the previous Õ(n^{5/6}ε^{-6}); a deterministic incremental (2r−1)-approximate APSP in Õ(m^{1/2}n^{1/r}) worst-case time follows as well. The approximation factors match the best known static oracle bounds, which the authors argue should be prioritized over running time, and an offline variant with Õ(m^{1/t+1}) average update and query time rules out conditional lower bounds for these approximations in the offline setting.

## Maximum Flow

1.  **Maximum flow and minimum-cost flow in almost-linear time.** FOCS 2022. [paper](https://doi.org/10.1109/FOCS54457.2022.00064)

    *Li Chen, Rasmus Kyng, Yang P. Liu, Richard Peng, Maximilian Probst Gutenberg, Sushant Sachdeva.*

    Gives the first almost-linear-time (m^{1+o(1)}) algorithms for maximum flow and minimum-cost flow on directed graphs, resolving a long-standing open question by combining dynamic graph techniques, expander decompositions, and continuous optimization.

## Talks: design templates

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

## Talks: continuous methods

1. **Continuous Methods in Graph Algorithms (Part 2).** DIMACS CCICADA. [video](https://www.youtube.com/watch?v=ISsMYFt7z7k)

    *Rasmus Kyng.*

    Part 2 of Rasmus Kyng's tutorial on continuous methods in graph algorithms.
