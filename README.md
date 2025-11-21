README

This repository accompanies the manuscript and provides the simulation workflow used to demonstrate adaptive, cost-aware nanoindentation in compositional gradient libraries.

Contents

The repository contains one Jupyter notebook:

AENI_Gradient_Library_Workflow_v2.ipynb
Self-contained notebook implementing the complete simulation workflow, including cost modeling, Gaussian-process surrogate modeling, and adaptive measurement strategies.
All figures and results in the manuscript can be reproduced from this notebook.

A second file (AENI_Gradient_Library_Workflow.pdf) is included only as a static version with previously generated outputs for convenience.

Notebook Overview

The main notebook (AENI_Gradient_Library_Workflow_v2.ipynb) implements the following components:

1. Cost Model for Automated Nanoindentation

    Defines a measurement time model based on KLA iMicro/iNano instrument behavior.
    
    Includes stage-motion penalties, drift stabilization time, and load–hold–unload cost components.

2. Gaussian Process Surrogate Model

    Implements heteroscedastic and homoscedastic GP models for predicting mechanical properties along gradient combinatorial libraries.
    
    Includes ARD kernels for composition-sensitive length-scale diagnostics.

3. Measurement Cost Analysis for Grid-Based Approaches

    Simulates baseline grid indentation across gradient libraries.
    
    Computes total experiment time and compares grid density effects on measurement cost.

4. Simulated Ground-Truth Generation

    Generates a clean (noise-free) hardness field for evaluating algorithmic performance.
    
    Later sections introduce controlled noise to mimic real experimental conditions.

5. Reference (Non-Adaptive) Strategies

    Runs classical grid-based measurement strategies as a benchmarking baseline.
    
    Evaluates efficiency and information gain relative to adaptive approaches.

6. Adaptive Gaussian-Process Workflow

    This section builds the complete cost-aware adaptive workflow:
    
    1.  Dynamic Drift Control
    
        Simulates decision-making strategies for when to perform drift correction.
    
        Demonstrates how drift affects both total time and uncertainty.
    
    2. Heteroscedastic GP With Noisy Ground Truth
    
        Introduces spatially varying noise into the synthetic hardness field.
    
        Fits GPs that explicitly model noise variations during adaptive indentation.
    
    3. Grid-Size Decision Simulations
    
        Evaluates how the choice of initial grid spacing influences time, uncertainty, and convergence.
    
    4.  Local Safe-Zone Definition and Meta-Grid Simulation
    
        Implements “safe zones’’ to restrict indentation to regions with acceptable uncertainty or composition.
    
        Runs meta-grid simulations to compare exploration vs. exploitation balance under cost constraints.
