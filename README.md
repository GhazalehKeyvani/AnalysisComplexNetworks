# Analysis in Complex Networks

---

## Datasets

- Synthetic Network (Erdős–Rényi)  
  Generated in-code to serve as a controlled baseline for centrality and diffusion experiments.

- Bitcoin User Network (Elliptic)  
  Derived from `elliptic_txs_classes.csv`, `elliptic_txs_edgelist.csv`, `elliptic_txs_features.csv` to model financial transaction links among users.

- Urban Mobile Communication Network  
  Real-world call and message interactions among city residents (see 1477c4_edc2.pdf).

---

## Results by Dataset

| Dataset                         | Diffusion Model | Top Centrality Metric      | Precision@10 | AUC   | Modularity | Notes                                                    |
|---------------------------------|-----------------|----------------------------|--------------|-------|------------|----------------------------------------------------------|
| Erdős–Rényi Synthetic           | IC / LT         | PageRank, Betweenness      | 0.56         | 0.60  | 0.12       | IC spreads faster with small seed sets; weak community structure. |
| Bitcoin User Network (Elliptic) | IC              | Betweenness                | 0.80         | 0.75  | 0.28       | Seed sizes 10–20 gave best average influence; PageRank fluctuates. |
| Urban Mobile Communication      | LT              | Closeness                  | 0.74         | 0.82  | 0.45       | LT benefits from larger seeds; strong, tightly-knit clusters. |

---

## Key Findings

- nodes with high betweenness centrality consistently act as bridges, enabling broader influence spread under the independent cascade model.  
- closeness centrality shines in threshold-based diffusion on networks with pronounced community modularity.  
- real-world topologies (bitcoin and mobile) yield higher modularity and predictive accuracy than random graphs.  
- combining precision@10 with AUC offers a balanced view of seed-selection effectiveness across different diffusion paradigms.  

---

### Next Steps

- incorporate link-prediction metrics (e.g., ROC curves on withheld edges) to extend community discovery insights.  
- explore hybrid diffusion models that mix cascade and threshold dynamics for networks with mixed interaction types.  
- visualize temporal evolution of influence spread using animated graphs in your README or LinkedIn post.
