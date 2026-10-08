---
title: MISO
summary: Model building from Identity, Sequence and Observed location. A workflow that turns SPM images of flexible biomolecules (glycans, glycoconjugates) into 3D molecular models, integrated into SXM Viewer.
date: 2026-10-08
type: docs
math: false
tags:
  - Software
  - Scanning probe microscopy
  - Glycoconjugates
image:
  caption: 'MISO'
---

## Description

**MISO** (**M**odel building from **I**dentity, **S**equence, and **O**bserved location) is a workflow for generating three-dimensional models of biomolecules from scanning probe microscopy (SPM) images. Interpreting SPM images of flexible biomolecules such as glycans and glycoconjugates is usually done by hand: building candidate adsorption geometries one by one and testing them. MISO automates this step.

The user provides a hypothesis about:

- the **identity** of the subunits (e.g. which monosaccharides),
- their **sequence** (how they are connected), and
- the **observed location** of each subunit in the SPM image.

MISO then builds structures consistent with that hypothesis. It aligns each monomer with the quaternion estimator algorithm (QUEST) and refines the polymer with biased classical molecular dynamics on the surface. Applied to existing SPM data of glycans and glycoconjugates, MISO reproduces structures previously validated by DFT. It can also filter out inconsistent hypotheses, and it scales up to a 3D model of an unfolded glycoprotein on a surface.

This work is described in **[Automating Model Building for SPM Images of Biomolecules Using MISO](https://doi.org/10.1021/acs.jcim.6c01134)**, *J. Chem. Inf. Model.* 66, 10056–10069 (2026).

Get the code from the [repository](https://github.com/Anggara-Group/MISO).

## MISO in SXM Viewer

The repository extends [SXM Viewer](https://github.com/Ex-libris/sxm_viewer), a desktop application for SPM data analysis (Anfatec/Omicron and Nanonis), with MISO tools, so the whole pipeline runs from the viewer:

1. Open an `.sxm` scan in SXM Viewer.
2. **Tools → Position coordinates**: toggle *Pick mode* and click on each molecule. The XY position (Å) and local height are recorded.
3. **Export CSV**: saves the molecule positions together with the STM grid (NPZ).
4. **Tools → Run MISO**: select the YAML configuration and the positions CSV, then set the number of iterations, polymers, compression steps and surface gravity.
5. The optimized structures are written to a `results/` folder as `.sdf`, `.mol` and `.mol2`.

## References

1. C. L. Gómez-Flores and K. Anggara. Automating Model Building for SPM Images of Biomolecules Using MISO. J. Chem. Inf. Model. 66, 10056–10069 (2026). https://doi.org/10.1021/acs.jcim.6c01134
2. SXM Viewer by Ex-libris. https://github.com/Ex-libris/sxm_viewer


## Did you find this page helpful? Consider sharing it 🙌
