# Project-Structural-Data-Analysis-on-Python

Read and combine multiple FoldX .fxout files.
Clean and rename columns for easier analysis.
Generate plots for each variable and save them as PDFs.
Bash commands for running FoldX can be run in JupyterLab using the %bash magic command.


FoldX Analysis of Protein Variants
Overview
This repository contains a comprehensive analysis of protein variants using the FoldX software. FoldX is a powerful tool for predicting the stability of protein structures based on various parameters. This analysis focuses on comparing the stability of different variants and identifying those with optimal characteristics for further study.

Table of Contents
Introduction
Folder Structure
Parameters
How to Use
Results
Conclusion
Introduction
Proteins are fundamental molecules that perform a vast array of functions in living organisms. Understanding the stability of protein structures is crucial for elucidating their biological roles and for applications in drug design, protein engineering, and biotechnology.

FoldX is a widely used computational tool that predicts the stability changes of protein structures based on amino acid mutations. It evaluates various energy parameters to assess the impact of mutations on protein stability.

Folder Structure
scss
Copy code
/output
    └── *.fxout (FoldX output files)
    
/Plots
    └── *.pdf (Generated plots from the analysis)
    
combined_foldx_data.csv (Combined data from all FoldX outputs)
README.md (This file)
Parameters
The following parameters are evaluated in this analysis:

Total Energy: The overall stability of the protein variant.
Backbone H Bond: Contributions from hydrogen bonds involving the backbone atoms.
Side Chain H Bond: Contributions from hydrogen bonds involving side chain atoms.
Van der Waals: Contributions from van der Waals interactions.
Electrostatics: Contributions from electrostatic interactions.
Polar Solvation: Contributions from polar solvation effects.
Hydrophobic Solvation: Contributions from hydrophobic solvation effects.
Van der Waals Clashes: Energy penalties due to atomic overlaps.
Side Chain Entropy: Entropic contributions from side chain conformational flexibility.
Main Chain Entropy: Entropic contributions from main chain flexibility.
S Loop Entropy: Entropic contributions from the S-loop conformations.
M Loop Entropy: Entropic contributions from the M-loop conformations.
Cis Bond: Contributions from cis peptide bonds.
Torsional Clash: Energy penalties due to torsional clashes.
Backbone Clash: Energy penalties due to clashes involving backbone atoms.
Helix Dipole: Contributions from the helical dipole.
Water Bridge: Contributions from water-mediated interactions.
Disulfide: Contributions from disulfide bonds.
Electrostatic Kon: Contributions from electrostatic interactions.
Partial Covalent Bonds: Contributions from partial covalent interactions.
Energy Ionisation: Contributions from energy changes upon ionization.
Entropy Complex: Contributions from complex formation entropy.
Residue Number: The position of the residue within the protein sequence.
How to Use
Place your FoldX output files in the output directory.
Run the analysis script to combine the data and generate plots:
bash
Copy code
python your_script.py
The results will be saved in the combined_foldx_data.csv file, and plots will be generated in the Plots folder.
Results
The analysis results include a combined CSV file with stability parameters for each protein variant, as well as visualizations that illustrate the differences in stability between the variants.

Conclusion
This repository serves as a foundation for further investigation into the stability of protein variants. Future work may include additional statistical analyses, validation against experimental data, and exploration of further modifications to enhance protein stability.
