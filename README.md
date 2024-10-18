# Project-Structural-Data-Analysis-on-Python

Table of Contents
Read and combine multiple FoldX .fxout files.
Clean and rename columns for easier analysis.
Generate plots for each variable and save them as PDFs.
Bash commands for running FoldX can be run in JupyterLab using the %bash magic command.


FoldX Analysis of Protein Variants
This repository contains a comprehensive analysis of protein variants using the FoldX software. FoldX is a powerful tool for predicting the stability of protein structures based on various parameters. This analysis focuses on comparing the stability of different variants and identifying those with optimal characteristics for further study.

This repository facilitates the analysis of protein variants using the FoldX software. FoldX is a computational tool that predicts the stability of protein structures based on various parameters, enabling researchers to compare different variants and identify those with optimal characteristics for further study. The analysis includes reading and combining multiple FoldX `.fxout` files, cleaning and renaming columns for easier analysis, and generating plots for each variable, which are saved as PDFs.

## Folder Structure
/output
    └── *.fxout (FoldX output files)
/Plots
    └── *.pdf (Generated plots from the analysis)
combined_foldx_data.csv (Combined data from all FoldX outputs)
README.md (This file)

## Parameters
The following parameters are evaluated in this analysis:
- Total Energy
- Backbone H Bond
- Side Chain H Bond
- Van der Waals
- Electrostatics
- Polar Solvation
- Hydrophobic Solvation
- Van der Waals Clashes
- Side Chain Entropy
- Main Chain Entropy
- S Loop Entropy
- M Loop Entropy
- Cis Bond
- Torsional Clash
- Backbone Clash
- Helix Dipole
- Water Bridge
- Disulfide
- Electrostatic Kon
- Partial Covalent Bonds
- Energy Ionisation
- Entropy Complex
- Residue Number

## How to Use
Place your FoldX output files in the output directory. To run FoldX, execute the following script in your terminal:
```bash
# Create a text file including all your pdb file names saved in one folder as a list
#!/bin/bash

# Specify the directory where your PDB files are
pdb_directory="/Users/nusinnaki/Desktop/ETH ZURICH/Reddy Lab/Thesis Project/Computational/2.FoldX/RBD his pdb"

# Change the working directory to the specified directory
cd "$pdb_directory"

# Generate the file_names.txt in the desired directory
output_directory="/Users/nusinnaki/Desktop/ETH ZURICH/Reddy Lab/Thesis Project/Computational/2.FoldX/"
ls > "$output_directory/file_names.txt"

# Run the FoldX executable in a loop using the list having your file names.
# Specify the output directory
output_dir="/Users/nusinnaki/Desktop/ETH ZURICH/Reddy Lab/Thesis Project/Computational/2.FoldX/Output"

# Specify the path to the FoldX executable
foldx_executable="/Volumes/reddy/Individual_Folders/Rakuhn/RK024/FoldX/foldx5MacStd.tar_/foldx_20231231"

# Change to the output directory
cd "$output_dir"

# Read the list of PDB file names from file_names.txt and process them one by one
while IFS= read -r pdb_file; do
    # Run FoldX for the current PDB file
    "$foldx_executable" --command=Stability --pdb="$pdb_file" --pdb-dir="/Users/nusinnaki/Desktop"
done < "/Users/nusinnaki/Desktop/ETH ZURICH/Reddy Lab/Thesis Project/Computational/2.FoldX/file_names.txt"

# After running FoldX, you will have files in your Output folder such as file_name_0_ST.fxout
