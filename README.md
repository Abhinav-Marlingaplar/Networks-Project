# Network Robustness in Scale-Free Networks

Designing robust scale-free networks under targeted attacks using local information.

Based on the report: "Designing robust scale-free networks under targeted link
attack using local information"

---

## Overview

This project replicates and extends the work of Tomassini (2023) on improving the robustness of scale-free networks under targeted edge attacks.

The study focuses on:
- Replicating the original edge-attack optimization method
- Evaluating robustness using the R-index metric
- Extending the analysis to node attack scenarios
- Comparing multiple network architectures

---

## Key Results

### Edge Attack (Replication)
- Original BA Network: R = 0.531  
- Optimized Network: R = 0.684  
- Improvement: +28.9% (exceeds ~17% reported in paper)

### Node Attack (Extension)
- BA Original: R ≈ 0.121  
- BA Optimized: R ≈ 0.126  
- Minimal improvement (~4%)

### Model Comparison

| Model           | Edge Robustness | Node Robustness |
|----------------|----------------|-----------------|
| BA Original    | 0.531          | 0.121           |
| BA Optimized   | 0.684          | 0.126           |
| Erdos-Renyi    | 0.555          | 0.231           |
| Small-World    | 0.533          | 0.252           |

---

## Methodology

### Network Model
- Barabási-Albert (BA) model  
- N = 200 nodes, m = 2  
- Scale-free structure with power-law degree distribution  

### Attack Strategies
- Targeted edge removal (highest edge degree)
- Targeted node removal (highest degree nodes)

### Robustness Metric

R-index (area under LCC curve):

R = (1/N) × Σ S(Q/N)

Higher R indicates greater robustness.

---

## Optimization Algorithm

Degree-preserving edge-swap heuristic:

1. Select two edges (a,b) and (c,d)  
2. Swap → (a,d), (c,b)  
3. Ensure no self-loops or duplicate edges  
4. Compute R-index  
5. Accept swap if R improves  
6. Repeat (~5000 iterations)  

Constraint: Node degrees remain unchanged.

---

## Key Insights

- Scale-free networks are robust to random failures but vulnerable to targeted attacks.
- Edge-swap optimization improves robustness by increasing disassortativity.
- Optimization redistributes connections from hub-to-hub to hub-to-periphery.
- Robustness is attack-specific:
  - Optimized BA performs best under edge attacks
  - Erdos-Renyi and Small-World perform better under node attacks

---

## Experiments

- Degree distribution analysis (power-law validation)
- Centrality measures:
  - Degree
  - Betweenness
  - Closeness
  - Eigenvector
- Clustering coefficient and modularity
- Edge attack simulation
- Node attack simulation
- Cross-model comparison

---

## Results and Visualizations

![Image](images/Screenshot%20from%202026-03-29%2016-45-46.png)
![Image](images/Screenshot%20from%202026-03-29%2016-46-13.png)
![Image](images/Screenshot%20from%202026-03-29%2016-46-32.png)
![Image](images/Screenshot%20from%202026-03-29%2016-46-55.png)
![Image](images/Screenshot%20from%202026-03-29%2016-47-06.png)
![Image](images/Screenshot%20from%202026-03-29%2016-47-28.png)
![Image](images/Screenshot%20from%202026-03-29%2016-47-41.png)
![Image](images/Screenshot%20from%202026-03-29%2016-47-57.png)
![Image](images/Screenshot%20from%202026-03-29%2016-48-10.png)
![Image](images/Screenshot%20from%202026-03-29%2016-48-26.png)
![Image](images/Screenshot%20from%202026-03-29%2016-48-50.png)
![Image](images/Screenshot%20from%202026-03-29%2016-49-07.png)
![Image](images/Screenshot%20from%202026-03-29%2016-49-22.png)

---

## Applications

- Internet and communication networks
- Power grid infrastructure
- Transportation systems
- Distributed systems design

---

## Limitations

- Single network instance (no averaging)
- Parameter sensitivity in Small-World model
- No weighted network analysis

---

## Future Work

- Hybrid optimization for node and edge attacks
- Testing on real-world datasets
- Extension to weighted networks
- Analysis of robustness vs efficiency trade-offs

---

## References

- Tomassini, M. (2023)
- Barabási, A.-L., & Albert, R. (1999)
- Albert, R., Jeong, H., & Barabási, A.-L. (2000)
- Newman, M. E. J. (2018)
- NetworkX Documentation

---

## Author

Abhinav Marlingaplar  
B.Tech CSE (AI & Data Science)  
IIIT Kottayam
