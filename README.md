#       DIPLOMA THESIS 

#     Graph Partitioning 

**Theodoros Kesoglou**  
Department of Electrical and Computer Engineering  
Aristotle University of Thessaloniki, 2025  
Supervisor: Associate Prof. Nikolaos Atreas

---

## What is this?

This repository contains the Python implementation and interactive notebooks accompanying my diploma thesis on **graph partitioning algorithms**.

Graph partitioning is a fundamental problem in combinatorial optimization: given a graph with weighted edges, divide its nodes into groups such that the total weight of edges connecting different groups is minimized. It sounds simple — but finding the optimal solution is NP-hard, which is exactly what makes it interesting.

The thesis studies three distinct approaches to this problem, each with a different philosophy:

- **Spectral Clustering** — uses the eigenstructure of the graph Laplacian to embed nodes in a low-dimensional space, then clusters them with k-means. Elegant, globally-informed, but requires choosing k upfront.
- **Normalized Cut** — a spectral method that explicitly minimizes a balanced cut criterion, avoiding the bias toward isolating small nodes that plain min-cut suffers from. Provably connected to the Rayleigh-Ritz quotient.
- **Kernighan-Lin** — a classic iterative heuristic that starts from an arbitrary partition and improves it through carefully chosen node swaps. Fast and practical. Also includes our own normalized variant of the algorithm.

---

## Repository Structure

```
graph-partitioning/
├── 01_introduction.ipynb          # Graph theory foundations & linear algebra tools
├── 02_spectral_clustering.ipynb   # K-Means + Spectral Clustering algorithm
├── 03_normalized_cut.ipynb        # Normalized Cut (single + recursive)
├── 04_kernighan_lin.ipynb         # Kernighan-Lin + custom variant + comparison
└── README.md
```

Each algorithm notebook is organized in three parts:
1. **Theory** — key definitions and formulas (brief, not a lecture)
2. **Implementation** — clean, documented Python code
3. **Results** — visualizations, metrics, iteration tables

---

## Dependencies

```bash
pip install numpy scipy matplotlib networkx scikit-learn pandas
```

All notebooks run with Python 3.8+. No GPU required.

---

## Background

The thesis covers:
- Graph representations: adjacency matrix, degree matrix, weight matrix
- The graph Laplacian and its spectral properties
- Characteristic polynomials and eigendecomposition
- Spectral Clustering (Donath & Hoffman 1973, Fiedler 1973)
- Normalized Cut (Shi & Malik 2000)
- Kernighan-Lin algorithm (1970) and a degree-normalized variant

**Keywords:** Graph Partitioning, Laplacian, Spectral Clustering, Normalized Cut, Kernighan-Lin

**If files cannot compile use: nbviewer.org File 1: https://nbviewer.org/github/teogr99/Graph_Partitioning/blob/main/01_introduction.ipynb
