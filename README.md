# Control Toolbox Benchmark: Optimization & Enrichment

This repository contains the final report of our Master's project (MAM4) at [Polytech Nice Sophia](https://polytech.univ-cotedazur.fr/). 

The project focuses on contributing to the open-source **[Control Toolbox](https://github.com/control-toolbox)**, a comprehensive Julia ecosystem dedicated to modeling, simulating, and solving Optimal Control Problems (OCPs). Our work was primarily centered around the `CTBenchmarks.jl` module.

**Authors:** Amiel Metier & Hédi Chennoufi  
**Supervisors:** Jean-Baptiste Caillau & Oliver Cots  

---

## Project Objectives & Key Contributions

Evaluating the efficiency of non-linear optimization solvers (like Ipopt or MadNLP) requires more than just average solving times. Our mission was to provide robust evaluation tools, fix convergence issues, and expand the benchmark library.

Here are our main contributions to the core repository:

### 1. Performance Profiles (Dolan-Moré)
- Implemented **Dolan-Moré performance profiles** to objectively compare `(model, solver)` pairs.
- Built a data-driven architecture using `DataFrames.jl` and `Plots.jl` to generate visual diagnostics measuring both **Efficiency** (speed) and **Robustness** (success rate).

### 2. Convergence Optimization & Bug Fixing
- Standardized the Min/Max objective definitions across different backends (JuMP, OptimalControl).
- Adjusted **Initial Guesses** based on physical realism to guide algorithms into the correct "basin of attraction," effectively eliminating "NA" failures and reducing solving times to industrial standards.

### 3. Hardware Acceleration (CPU vs GPU Benchmarking)
- Configured a dedicated benchmark (`core-kkt-gpu`) to compare the execution times of the KKT linear system resolution on standard Processors (CPU) vs Graphics Cards (GPU).
- Demonstrated the massive speed-up provided by the `(exa_gpu, madnlp)` configuration for large grid sizes.

### 4. Benchmark Enrichment
- Automated testing scenarios comparing **Midpoint** vs **Trapezoidal** time discretization methods.
- Reverse-engineered and integrated **4 new complex OCPs** into the library (assisted by Gemini CLI):
  - *Brachistochrone* (Time minimization)
  - *Bryson-Denham* (Strict state constraints)
  - *Mountain Car* (Underactuated dynamics)
  - *Balanced Field* (Aerospace takeoff constraints)

---

## Technologies & Tools
- **Language:** Julia 
- **Packages:** `OptimalControl.jl`, `ExaModels.jl`, `MadNLP.jl`, `Ipopt.jl`, `DataFrames.jl`, `Plots.jl`
- **Workflow:** Git, GitHub Actions (CI/CD), Atomic Commits, Pull Requests
- **AI Assistance:** Gemini CLI (Prompt Engineering inside VSCode)

---

## Documents
You can find the detailed documentation of our work in this repository:
- 📄 **[Full Project Report (PDF)](./Rapport_optimalcontrole_Metier.pdf)** *(in French)*

---
