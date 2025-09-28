# SIMPOL Model (v6+)

**Author:** Ricardo Alonzo Fernández Salguero  

This repository contains the implementation of the **SIMPOL model**, an agent-based and numerical framework for solving Hamilton–Jacobi–Bellman (HJB) equations with policy post-processing, Fokker–Planck (FPK) stationary distributions, and robust validation checks.

---

##  Features

- **Modular architecture**: configuration, solver, diagnostics.  
- **HJB (Howard iteration)** with post-processed policy: smoothing + slope band `c'(a) ∈ [r+smin, r+smax]`.  
- **FPK stationary distribution**: exact zero-flux condition + normalization.  
- **Robust Wasserstein-2 check**: contraction verification under configurable time step (`dt`), horizon (`k`), and reflecting boundaries.  
- **Merton validation (σ=0, a ≥ 0 compatible)**:  
  - Interior solution exists iff `κ ≤ r`.  
  - Otherwise, the restricted optimum is `c = r a + y`.  
- **Final summary** with `EXPECT_TRUE` flags for quick one-glance validation.

---

## Requirements

- Python 3.9+
- Dependencies:  
  ```bash
  pip install numpy

