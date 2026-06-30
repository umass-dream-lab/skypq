# Incremental Package Queries

[Vasileios Vittis](https://vvittis.github.io/) · [Azza Abouzied](http://azza.azurewebsites.net/) · [Peter J. Haas](https://people.cs.umass.edu/~phaas/) · [Alexandra Meliou](https://people.cs.umass.edu/~ameli/)

[Project Website](https://umass-dream-lab.github.io/skypq) · [SKYPQ Live Demo](https://umass-dream-lab.github.io/skypq/demo.html)

## About

Incremental Package Queries extends database systems with efficient constrained optimization over dynamic data. We develop methods to maintain optimal solutions incrementally, avoiding expensive recomputation when data or query parameters change.

A *package query* returns a multiset of tuples satisfying global constraints and optimizing a given objective. Package queries enable in-database prescriptive analytics across domains such as finance, healthcare, logistics, and cloud computing.

## Works

### SKYPQ: Dominance-Based Data Reduction for Package Queries
*To appear at VLDB 2026 (Demonstration Track), PVLDB Vol. 19, Issue 12.*

When each attribute in a query has a clear "better" direction (e.g., lower cost, higher performance), most candidate tuples are irrelevant: they are strictly worse than others on every dimension and can never appear in an optimal solution. SKYPQ maintains a **K-skyband index** (a small, correctness-preserving subset of candidates) and applies a **re-solve checker** that skips re-optimization when an update cannot affect the optimal package. The index can be shared across package queries with the same preference directions.

- **Live demo:** https://umass-dream-lab.github.io/skypq/demo.html
- **Paper:** [`papers/paper.pdf`](papers/paper.pdf)
- **Code:** the entire SKYPQ demo is a single self-contained file, [`demo.html`](demo.html) (see below).

## Code & artifacts

**The complete SKYPQ demo is implemented in one file, [`demo.html`](demo.html)** — there is **no backend and no build step**. The ILP solver, K-skyband computation, incremental maintenance, the re-solve checker, and the interactive UI all run **client-side in the browser**; open `demo.html` (or visit the live demo) and it runs offline. The only external dependencies are two CDN libraries: **D3** (rendering) and **[HiGHS](https://highs.dev/)** (an industrial MILP solver compiled to WebAssembly, which produces the *exact* optimum).

Map of the paper's concepts to the code (search inside `demo.html`):

| Paper concept | Code (function / section) |
|---|---|
| Dominance | `// DOMINANCE` → `dominates()`, `getPointsDominatedBy()` |
| K-skyband reduction | `// PARETO` → `computeSkyband()` |
| Exact ILP over the skyband | `// ILP SOLVER (HiGHS)` → `solveILP()`, `solveOpt()` |
| Incremental maintenance + promotion | `recomputeAllSteps()` (playground edits: add / delete / drag) |
| Re-solve checker (skip when optimum can't change) | `recomputeAllSteps()` → `needResolve` |
| Shared skyband across PQs | `// KULLI TAB FUNCTIONS` → `solveKulliQuery()` |

The reduction only *shrinks* the solver's input; the optimum is always produced by HiGHS over the reduced set, so results are exact, never approximate.

## Repository contents

```
demo.html        SKYPQ demo — the complete system (engine + UI, single file, no backend)
index.html       project website (served via GitHub Pages)
papers/          papers and posters (paper.pdf = SKYPQ demo paper)
assets/          logos and screenshots
```

## License

MIT License
