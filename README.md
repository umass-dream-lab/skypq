# Incremental Package Queries

[Vasileios Vittis](https://vvittis.github.io/) · [Azza Abouzied](http://azza.azurewebsites.net/) · [Peter J. Haas](https://people.cs.umass.edu/~phaas/) · [Alexandra Meliou](https://people.cs.umass.edu/~ameli/)

[Project Website](https://umass-dream-lab.github.io/skypq) · [SKYPQ Live Demo](https://umass-dream-lab.github.io/skypq/demo.html)

## About

Incremental Package Queries extends database systems with efficient constrained optimization over dynamic data. We develop methods to maintain optimal solutions incrementally—avoiding expensive recomputation when data or query parameters change.

A *package query* returns a multiset of tuples satisfying global constraints and optimizing a given objective. Package queries enable in-database prescriptive analytics across domains like finance, healthcare, logistics, and cloud computing.

## Works

**SKYPQ: Dominance-Based Data Reduction for Package Queries** *(Under Submission)*

Prescriptive analytics workloads often require solving package queries over data that changes continuously. When each attribute in the query has a clear "better" direction, e.g., lower cost and higher performance, most candidate tuples are irrelevant: they are strictly worse than others on every dimension and can never appear in an optimal solution. We demonstrate SKYPQ, a system that employs a novel, dominance-based data reduction method for package queries under updates. The key idea is to maintain a K-skyband index, a small, correctness-preserving subset of candidates, and apply a resolve checker to skip re-optimization when updates cannot affect the optimal package.

## License

MIT License
