# Supplementary Materials: Computational Drug Discovery Against Pseudomonas aeruginosa

## Overview
This directory contains supplementary materials for a comprehensive computational drug discovery study targeting Pseudomonas aeruginosa, a notorious opportunistic pathogen known for its antibiotic resistance. The research employs multiple computational approaches including molecular docking, molecular dynamics simulations, density functional theory (DFT) analysis, and genomics analysis to identify potential therapeutic compounds.

## Research Context
Pseudomonas aeruginosa is a Gram-negative bacterium that causes severe infections in immunocompromised patients, particularly those with cystic fibrosis, burns, or cancer. The organism's remarkable ability to develop resistance to multiple antibiotics makes it a significant challenge in clinical settings. This study focuses on identifying novel therapeutic compounds through computational approaches.

## Directory Structure

### 1. Database Query for Ligands Acquisition
**Location**: `Database query fro ligands acquisitiom/`

Contains initial compound libraries organized into four groups

All compounds were downloaded from PubChem database and pharmacophore modeling was used to generate pharmer.query files for Zinc12 database searching.

### 2. Ligands for Molecular Docking
**Location**: `Ligands for molecular docking/`

Contains the processed ligand files (SDF format) for each group and the target protein structure:
- `Group A.sdf`, `Group B.sdf`, `Group C.sdf`, `Group D.sdf`
- `MvfR__alphafold2.pdb` - Target protein structure (MvfR transcriptional regulator)

### 3. Docking Scores
**Location**: `Docking scores/`

Contains CSV files with molecular docking results for each compound group:
- `group A.csv`, `Group B.csv`, `group C.csv`, `Group D.csv`

**Note**: The number of docked conformations exceeds input compounds as Maestro generates multiple possible conformations for each ligand.

### 4. Molecular Dynamics Simulations
**Location**: `Simulations/`

Contains molecular dynamics simulation data and analysis:
- **Data files**: Various `.xvg` files containing simulation trajectories and analysis data
- **Comparison plots**: PNG files showing comparative analysis across compound groups:
  - `hbdist_comparison.png` - Hydrogen bond distance analysis
  - `protein_ligand_HBA_HBD_comparison.png` - Hydrogen bond acceptor/donor analysis
  - `protein_ligand_hbonds_comparison.png` - Hydrogen bonding patterns
  - `resarea_comparison.png` - Residue area analysis
  - `rmsd_ca_comparison-4.png` - Root mean square deviation analysis
  - `rmsf_ca_comparison-3.png` - Root mean square fluctuation analysis
  - `rog_prot_comparison-2.png` - Radius of gyration analysis
  - `sasa_com_comparison-2.png` - Solvent accessible surface area analysis

### 5. MM-GBSA Analysis
**Location**: `mmgbsa/`

Contains molecular mechanics generalized Born surface area (MM-GBSA) binding energy calculations:
- `group A.csv`, `Group B.csv`, `Group C.xlsx`, `Group D.xlsx`

### 6. DFT Analysis
**Location**: `DFT analysis/`

Contains density functional theory calculations for lead compounds:
- **Compound folders**: `A1/`, `B1/`, `C1/`, `D1/` - Each containing:
  - Input files (`.inp`, `.xyz`)
  - Output files (`.out`)
  - Molecular orbital visualizations (HOMO/LUMO images)
  - 3D structure files (`.pdb`)
- `Results of Derived Electronic and Reactivity Parameters of Lead Compounds.docx` - Comprehensive analysis report

### 7. Genomics Results from PATRIC Pipeline
**Location**: `Genomics results from PATRIC pipeline/`

Contains genomic analysis results:
- `Analysis _sp_gene.csv` - Comprehensive gene analysis including virulence factors, antibiotic resistance genes, transporters, and drug targets
- `Genome_feature-2.csv` - Genome feature analysis

### 8. Top Performing Compounds
**Location**: `Top performing compounds/`

Contains the final lead compounds identified from the study:
- `A1.pdb` - Top fluoroquinolone derivative
- `B1.pdb` - Top cephalosporin derivative  
- `C1.pdb` - Top aminoglycoside derivative
- `D1.pdb` - Top levofloxacin derivative

## Research Methodology

### Computational Pipeline
1. **Compound Library Generation**: Pharmacophore-based database searching using PubChem compounds
2. **Molecular Docking**: Structure-based virtual screening against MvfR target
3. **Molecular Dynamics**: 100ns simulations to assess binding stability
4. **MM-GBSA Analysis**: Binding energy calculations
5. **DFT Analysis**: Electronic structure and reactivity analysis
6. **Genomics Analysis**: PATRIC pipeline for virulence and resistance gene identification

### Target Protein
**MvfR (Multiple Virulence Factor Regulator)**: A transcriptional regulator involved in quorum sensing and virulence factor expression in P. aeruginosa. Inhibition of MvfR represents a novel therapeutic strategy targeting bacterial communication rather than growth.

## Key Findings
- Identification of four lead compounds (A1, B1, C1, D1) with promising binding affinities
- Molecular dynamics simulations confirm stable protein-ligand complexes
- DFT analysis reveals favorable electronic properties for drug development
- Genomics analysis identifies multiple resistance mechanisms and virulence factors


## Software Used
- **Molecular Docking**: Maestro/Schrodinger Suite
- **Molecular Dynamics**: GROMACS
- **Quantum Chemistry**: Gaussian (DFT calculations)
- **Genomics**: PATRIC pipeline
- **Visualization**: Various molecular visualization tools

## For more information
Do reach out to Correspondence: t.ibisanmi@unsw.edu.au (T.I.A.); n.kumar@unsw.edu.au (N.K.)