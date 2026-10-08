---
title: Sugar SMILES Finder
summary: A web app that finds a sugar by name in PubChem and returns its SMILES, InChIKey and 3D structure, with optional control over ring puckering, anomer and D/L configuration.
date: 2026-10-08
type: docs
math: false
tags:
  - Web app
  - Carbohydrates
  - Cheminformatics
image:
  caption: 'Sugar SMILES Finder'
---

## Description

**Sugar SMILES Finder** is a small [Streamlit](https://streamlit.io/) app for quickly getting machine-readable structures of carbohydrates. Type the name of a sugar (e.g. *glucose*, *sucrose*, *α-L-fucose*). The app searches [PubChem](https://pubchem.ncbi.nlm.nih.gov/) and shows the isomeric and connectivity SMILES, InChIKey, molecular formula, molecular weight, IUPAC name, and an interactive 3D structure.

Open the app directly via the [site link](https://sugar-smiles.streamlit.app/).

## Simple search

Enter a name and press **Search**. You get the PubChem entry with its SMILES (ready to copy) and the PubChem 3D conformer in an interactive viewer.

## Advanced search

Tick the **Advanced search** box to choose the exact form of the sugar and the conformation of its ring:

- **Ring puckering**: chair (⁴C₁ or ¹C₄), boat or envelope
- **Anomer**: α or β
- **Configuration**: D or L

The anomer and D/L choices are used to build the PubChem query (e.g. *glucose* + α + D → *alpha-D-glucose*). Because SMILES does not encode ring conformation, the 3D structures are generated with [RDKit](https://www.rdkit.org/). The app embeds a conformer ensemble with ETKDG, optimises it with the MMFF94 force field, and classifies each ring using Cremer–Pople puckering parameters and IUPAC conformation names (e.g. ⁴C₁, B₂,₅, ²E).

Conformers that match the requested pucker are ranked by energy relative to the lowest-energy conformer found. If the requested pucker is not a relaxed minimum (for example, a boat for β-D-glucose), the app enforces it with ring-torsion restraints and reports the resulting strain energy. Each conformer can be viewed in 3D and downloaded as a `.mol` file.

## Source code

The code is available on [GitHub](https://github.com/tipiorgup/sugar-smiles-finder).

## References

1. S. Kim et al. PubChem 2023 update. Nucleic Acids Research 51, D1373–D1380 (2023). https://doi.org/10.1093/nar/gkac956
2. RDKit: Open-source cheminformatics. https://www.rdkit.org
3. S. Riniker and G. A. Landrum. Better Informed Distance Geometry: Using What We Know To Improve Conformation Generation. J. Chem. Inf. Model. 55, 2562–2574 (2015). https://doi.org/10.1021/acs.jcim.5b00654
4. T. A. Halgren. Merck molecular force field. I. Basis, form, scope, parameterization, and performance of MMFF94. J. Comput. Chem. 17, 490–519 (1996).
5. D. Cremer and J. A. Pople. General definition of ring puckering coordinates. J. Am. Chem. Soc. 97, 1354–1358 (1975). https://doi.org/10.1021/ja00839a011
6. IUPAC-IUB Joint Commission on Biochemical Nomenclature. Conformational nomenclature for five- and six-membered ring forms of monosaccharides and their derivatives. Eur. J. Biochem. 111, 295–298 (1980).


## Did you find this page helpful? Consider sharing it 🙌
