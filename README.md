# SIMPOL Model
**Author:** Ricardo Alonzo Fernández Salguero  
**Date:** September 28, 2025  

This repository contains the implementation of the **SIMPOL model** (Simplified Policy Iteration), a modular numerical framework for solving continuous-time heterogeneous agent problems.  

---

##  Overview

The SIMPOL model tackles the optimization of consumption and savings under idiosyncratic uncertainty.  
It formulates the problem as a coupled system of partial differential equations:  

- **Hamilton–Jacobi–Bellman (HJB)** equation for the agent’s optimal policy.  
- **Fokker–Planck–Kolmogorov (FPK)** equation for the stationary wealth distribution.  

### Key Features
- Modular architecture: configuration, solver, diagnostics.  
- HJB (Howard iteration) with policy post-processing: smoothing + slope band `c'(a) ∈ [r+smin, r+smax]`.  
- FPK stationary distribution with exact zero-flux normalization.  
- Wasserstein-2 contraction checks with configurable parameters.  
- Validation against the **Merton model** (σ = 0, a ≥ 0 compatible).  
- Final diagnostic summary with `EXPECT_TRUE` flags.  

---

##  Requirements

- Python 3.9+  
- Dependencies:  
  ```bash
  pip install numpy

* Optional (for plots and extended analysis):

  ```bash
  pip install matplotlib
  ```

---

##  Usage

Run the demo script to check convergence, FPK quality, W2 contraction, and Merton validation:

```bash
python simpol_model.py
```

This will produce console outputs including diagnostics and validation summaries, for example:

```
[RES/HJB] ||HJB||=2.1e-05 ; ||FOC||=3.2e-06 ; M=(True,True)
[Check/FPK] mass=1.0000 (ok=True) ; JL≈0.00e+00 ; JR≈0.00e+00 (ok=True)
[Check/W2] median=0.8567 IQR=(0.8221,0.8894) → contraction_ok=True
[EXPECT_TRUE] Merton_sigma0_ok: True
[ALL_OK] True
```

---

##  Repository Structure

* `simpol_model.py` → main implementation (HJB, FPK, W2, validation).
* `notebooks/` → reproducible Jupyter notebooks (optional).
* `README.md` → project description and usage instructions.

---

##  Citation

If you use this code, please cite the corresponding paper:

```bibtex
@misc{fernandezsalguero2025simpol,
  author       = {Ricardo Alonzo Fernández Salguero},
  title        = {SIMPOL Model for Solving Continuous-Time Heterogeneous Agent Problems},
  year         = {2025},
  howpublished = {arXiv preprint},
}
```

---

##  License

This project is licensed under the **MIT License** – see the [LICENSE](LICENSE) file for details.

---

##  Notes

* The preprint is available on **arXiv**: [arXiv:2509.xxxxx](https://arxiv.org/abs/2509.xxxxx) *(to be updated upon submission)*.
* A permanent archived version of the code will be available via [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.17216748.svg)](https://doi.org/10.5281/zenodo.17216748)





