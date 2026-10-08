---
title: Protein MD in Jupyter
summary: The classic lysozyme-in-water MD tutorial, re-created as intuitive Jupyter notebooks for GROMACS and OpenMM.
date: 2026-10-08
type: docs
math: false
tags:
  - Simulations
  - Molecular Dynamics
image:
  caption: 'Lysozyme in water with GROMACS and OpenMM'
---
## Description

This is **not a new tutorial**. It is a re-creation of the classic protein MD tutorial,
[Lysozyme in Water by Justin A. Lemkul](http://www.mdtutorials.com/gmx/lysozyme/index.html),
rewritten as **Jupyter notebooks** to make it more intuitive and hands-on. Instead of
typing commands one by one in a terminal, every step lives in a notebook cell, with
comments explaining what it does, so you can run, modify and re-run the workflow and
plot the results in the same place.

The same system (hen egg-white lysozyme, PDB **1AKI**) is simulated with two platforms:

- **GROMACS**: the original workflow, driven from Python with GromacsWrapper.
- **OpenMM**: the same workflow written in pure Python, which I find has a gentler learning curve if you already know Python.

Find the notebooks on GitHub: **[tipiorgup/MDtutorials](https://github.com/tipiorgup/MDtutorials/tree/main)**

## Workflow

1. Clean the crystal structure (remove crystallographic waters).
2. Build the topology and choose a force field.
3. Define the simulation box and solvate it.
4. Add ions to neutralize the system.
5. Minimize the energy.
6. Equilibrate under NVT, then NPT.
7. Run the production MD.
8. Analyze the results, e.g. plot the potential energy.

## Folder Structure

- **GROMACS**: `GROMACS_playground.ipynb` plus the `.mdp` parameter files in `scripts/` (ions, minimization, NVT, NPT, MD).
- **OPENMM**: `OPENMM_playground.ipynb` (CHARMM36 force field, minimization, NVT/NPT and production with reporters).
- **structures**: The 1AKI input structure, raw and cleaned.

## Setting Up OpenMM

```bash
conda create -n openmm
conda activate openmm
conda install -c conda-forge openmm numpy matplotlib jupyter
```

## References

1. J. A. Lemkul. From Proteins to Perturbed Hamiltonians: A Suite of Tutorials for the GROMACS-2018 Molecular Simulation Package. Living Journal of Computational Molecular Science (2018), 1(1):5068. DOI: 10.33011/livecoms.1.1.5068
2. M. J. Abraham et al. GROMACS: High performance molecular simulations through multi-level parallelism from laptops to supercomputers. SoftwareX (2015), 1–2:19–25. DOI: 10.1016/j.softx.2015.06.001
3. P. Eastman et al. OpenMM 8: Molecular Dynamics Simulation with Machine Learning Potentials. J. Phys. Chem. B (2024), 128(1):109–116. DOI: 10.1021/acs.jpcb.3c06662

## Did you find this page helpful? Consider sharing it 🙌
