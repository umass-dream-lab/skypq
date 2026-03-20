# Incremental Package Queries

This repository hosts the project website for **Incremental Package Queries** research.

🌐 **Live Site**: [https://umass-dream-lab.github.io/skypq/](https://umass-dream-lab.github.io/skypq/) *(coming soon)*

## About

**Incremental Package Queries** extends database systems with efficient constrained optimization over dynamic data. We develop methods to maintain optimal solutions incrementally—avoiding expensive recomputation when data or query parameters change.

A *package query* returns a collection of tuples that collectively optimize an objective function while satisfying constraints. Package queries enable in-database prescriptive analytics across domains like finance, healthcare, logistics, and cloud computing.

## Demo

The **SKYPQ Demo** demonstrates K-skyband-based data reduction for package queries:

- Watch 6,500 VM offers collapse to a small K-skyband (~58 candidates)
- Compare greedy heuristics against exact ILP solutions
- Trigger what-if scenarios (price changes, VM discontinuation)
- Interactive playground for manual exploration

## Files

| File | Description |
|------|-------------|
| `index.html` | Project landing page |
| `demo.html` | Interactive SKYPQ demo (runs entirely in browser) |
| `screenshot.html` | Zoomable screenshot viewer |
| `screenshot.png` | Demo screenshot |

## Publications

- **SKYPQ: K-Skyband Data Reduction for Package Queries**  
  Vasileios Vittis, Azza Abouzied, Peter J. Haas, Alexandra Meliou  
  *VLDB 2026 (Demo)*

- **Incremental Package Maintenance**  
  Vasileios Vittis, Azza Abouzied, Peter J. Haas, Alexandra Meliou  
  *NEDB 2025 (Poster)* — [Project Page](https://vvittis.github.io/ScalablePackageBuilderProject/)

## Related Work

This research builds on the [Package Queries](https://packagebuilder.cs.umass.edu/) project:

- Brucato et al., *Scalable Package Queries in Relational Database Systems*, VLDB 2016 — [PDF](https://vldb.org/pvldb/vol9/p576-brucato.pdf)
- Mai et al., *Scaling Package Queries to a Billion Tuples*, VLDB 2024 — [PDF](https://www.vldb.org/pvldb/vol17/p1146-mai.pdf)

## People

- [Vasileios Vittis](https://vvittis.github.io/) — PhD Student, UMass Amherst
- [Azza Abouzied](http://azza.azurewebsites.net/) — Professor, NYU Abu Dhabi
- [Peter J. Haas](https://people.cs.umass.edu/~phaas/) — Professor, UMass Amherst
- [Alexandra Meliou](https://people.cs.umass.edu/~ameli/) — Professor, UMass Amherst

## Acknowledgements

This work is supported by NSF grants IIS-1943971 and IIS-1421322.

## License

MIT License
