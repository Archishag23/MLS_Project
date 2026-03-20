ERM vs MARG-CTRL on Subsampled Data: Does Subsampling Help, Hurt, or Interact with Margin-Control Regularisation?

Machine learning models exploit shortcuts - spurious correlations like hospital logos in chest X-rays or image backgrounds in bird classification - achieving high in-distribution accuracy but failing under distribution shift. Margin-control (MARG-CTRL) losses (Puli et al., 2023) mitigate this by enforcing uniform margins, but their interaction with common data-balancing strategies is poorly understood.
This paper identifies the dimension-to-sample ratio $d/n$ as the single variable governing MARG-CTRL's success. 

We prove and empirically verify:

A sharp phase transition at $d/n = 1$: MARG-CTRL eliminates shortcut dependence when $d < n$, and its guarantees break completely when $d > n$.

Harmful Group-balanced downsampling: This strategy is harmful in exactly the high-$\rho$ regimes where shortcuts are most severe, because it pushes $d/n$ past the critical threshold.

Multi-shortcut elimination: The uniform-margin constraint eliminates multiple simultaneous shortcuts algebraically at no additional sample cost - the threshold remains $d < n$ regardless of the number of shortcuts.

Repository Structure

```
├── README.md
├── MLS_NEURIPS.pdf                 # Full paper
├── MLS_toy_experiments.ipynb       # Synthetic experiments (E1–E7)
└── real_data_experiments_FINAL.ipynb # Waterbirds & SpurBreast experiments
```
References:

Puli, A., Zhang, L., Wald, Y., & Ranganath, R. (2023). Don't blame dataset shift! Shortcut learning due to gradients and cross entropy.

Sagawa, S., et al. (2020). An investigation of why overparameterization exacerbates spurious correlations. ICML.
