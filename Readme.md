# Supplementary Materials: Computational Drug Discovery Against Pseudomonas aeruginosa

## Overview
This repository contains supplementary materials for a comprehensive computational drug discovery study targeting Pseudomonas aeruginosa, a notorious opportunistic pathogen known for its antibiotic resistance. The research employs multiple computational approaches including molecular docking, molecular dynamics simulations, density functional theory (DFT) analysis, scaffold analysis, physiochemical profiling, and genomics analysis to identify potential therapeutic compounds.

## Repository Description
This is a data repository comprising outputs from a multi-stage computational pipeline. It contains structured data files (CSV, SDF, PDB, XVG, XLSX), analysis results, and visualizations—not executable source code. The materials are organized by analysis type and compound group to support reproducibility and downstream use.

## Research Context
Pseudomonas aeruginosa is a Gram-negative bacterium that causes severe infections in immunocompromised patients, particularly those with cystic fibrosis, burns, or cancer. The organism's remarkable ability to develop resistance to multiple antibiotics makes it a significant challenge in clinical settings. This study focuses on identifying novel therapeutic compounds through computational approaches.

## Directory Structure

### 1. Database Query for Ligand Acquisition
**Location**: `Database query for ligand acquisition/`

Contains initial compound libraries organized into four groups (Fluoroquinolones, Cephalosporins, Aminoglycosides, Levofloxacin). All compounds were downloaded from the PubChem database and pharmacophore modeling was used to generate pharmer.query files for Zinc12 database searching.

### 2. Ligands for Molecular Docking
**Location**: `Ligands for molecular docking/`

Contains the processed ligand files (SDF format) for each group and the target protein structure:
- `Group A.sdf`, `Group B.sdf`, `Group C.sdf`, `Group D.sdf`
- `MvfR__alphafold2.pdb` — Target protein structure (MvfR transcriptional regulator)

### 3. Docking Scores
**Location**: `Docking scores/`

Contains CSV files with molecular docking results for each compound group:
- `group A.csv`, `Group B.csv`, `group C.csv`, `Group D.csv`

**Note**: The number of docked conformations exceeds input compounds as Maestro generates multiple possible conformations for each ligand.

### 4. Molecular Dynamics Simulations
**Location**: `Simulations/`

Contains molecular dynamics simulation data and analysis:
- **Data files** (`file/`): XVG files containing simulation trajectories and analysis data (RMSD, RMSF, radius of gyration, SASA, hydrogen bonding, etc.) for fluoroquinolone, cephalosporin, aminoglycoside, and levofloxacin complexes
- **Comparison plots**: PNG files showing comparative analysis across compound groups

### 5. MM-GBSA Analysis
**Location**: `mmgbsa/`

Contains molecular mechanics generalized Born surface area (MM-GBSA) binding energy calculations:
- `group A.csv`, `Group B.csv`, `Group C.xlsx`, `Group D.xlsx`

### 6. DFT Analysis
**Location**: `DF analysis/`

Contains density functional theory calculations for lead compounds:
- **Compound folders**: `A1/`, `B1/`, `C1/`, `D1/` — Each containing:
  - ORCA output files (`.out`)
  - Molecular orbital visualizations (HOMO/LUMO images)
  - Extracted DFT properties (`.csv`)
- `DFT_properties_consolidated.csv` — Consolidated electronic and reactivity parameters (HOMO, LUMO, band gap, dipole moment, hardness, softness, etc.)

### 7. Physiochemical Analysis
**Location**: `physiochemical/`

Contains physiochemical property analysis for compound groups A–D:
- **Group folders**: `group_A/`, `group_B/`, `group_C/`, `group_D/` — Each containing:
  - Mean physicochemical metrics (molecular size, compliance rates)
  - Compliance metrics and druglikeness data
  - Group-level CSV data files
  - PNG/PDF visualizations

### 8. Ligand Docking Interactions
**Location**: `ligand docking interraction/`

Contains detailed protein–ligand interaction data for top compounds:
- **Group folders**: `groupA/`, `groupb/`, `groupc/`, `groupd/` — Each containing:
  - CSV files with residue-level interaction descriptions (hydrogen bonds, pi-cation, electrostatic contacts)
  - Molecular structure images (`.jpeg`)

### 9. Ligand Motifs (Scaffold) Analysis
**Location**: `ligand motifs analysis/`

Contains scaffold-based analysis of top-performing compounds:
- **zinc_structures/**: SDF files for ZINC compounds
- **zinc_smiles/**: SMILES representations and group-level CSV files
- **result/**: Analysis outputs including:
  - `compound_to_scaffold_mapping.csv` — Compound–scaffold assignments with interaction metrics
  - `problem1_scaffold_frequency_in_top_compounds.csv` — Scaffold frequency in top hits
  - `problem2_scaffold_docking_performance.csv` — Docking performance by scaffold
  - `problem3_key_interactions_by_scaffold.csv` — Key interactions by scaffold family
  - `problem3_heatmap_scaffold_*.png/pdf` — Heatmap visualizations
  - `scaffold_analysis_comprehensive.csv` — Comprehensive scaffold metrics

### 10. Genomics Results from PATRIC Pipeline
**Location**: `Genomics results from PATRIC pipeline/`

Contains genomic analysis results:
- `Analysis _sp_gene.csv` — Comprehensive gene analysis including virulence factors, antibiotic resistance genes, transporters, and drug targets
- `Genome_feature-2.csv` — Genome feature analysis

### 11. Top Performing Compounds
**Location**: `Top performing compounds pdb/`

Contains the final lead compound structures identified from the study:
- `A1.pdb` — Top fluoroquinolone derivative
- `B1.pdb` — Top cephalosporin derivative
- `C1.pdb` — Top aminoglycoside derivative
- `D1.pdb` — Top levofloxacin derivative

## Research Methodology

### Computational Pipeline
1. **Compound Library Generation**: Pharmacophore-based database searching using PubChem compounds
2. **Molecular Docking**: Structure-based virtual screening against MvfR target
3. **Molecular Dynamics**: 100 ns simulations to assess binding stability
4. **MM-GBSA Analysis**: Binding energy calculations
5. **DFT Analysis**: Electronic structure and reactivity analysis (ORCA)
6. **Physiochemical Profiling**: Druglikeness and compliance metrics
7. **Scaffold Analysis**: Structural scaffold identification and performance mapping
8. **Genomics Analysis**: PATRIC pipeline for virulence and resistance gene identification

### Target Protein
**MvfR (Multiple Virulence Factor Regulator)**: A transcriptional regulator involved in quorum sensing and virulence factor expression in P. aeruginosa. Inhibition of MvfR represents a novel therapeutic strategy targeting bacterial communication rather than growth.

## Key Findings
- Identification of four lead compounds (A1, B1, C1, D1) with promising binding affinities
- Molecular dynamics simulations confirm stable protein–ligand complexes
- DFT analysis reveals favorable electronic properties for drug development
- Scaffold analysis identifies recurring structural motifs among top performers
- Physiochemical profiling supports druglikeness of lead compounds
- Genomics analysis identifies multiple resistance mechanisms and virulence factors

## File Formats
| Format | Use |
|--------|-----|
| CSV | Docking scores, MM-GBSA, DFT properties, scaffold mappings, interaction data |
| SDF | Ligand structures, ZINC compound libraries |
| PDB | Protein structure, lead compound coordinates |
| XVG | GROMACS trajectory and analysis outputs |
| XLSX | MM-GBSA results (Groups C, D) |
| PNG/PDF | Plots and visualizations |

## Software Used
- **Molecular Docking**: Maestro/Schrodinger Suite
- **Molecular Dynamics**: GROMACS
- **Quantum Chemistry**: ORCA (DFT calculations)
- **Genomics**: PATRIC pipeline
- **Visualization**: Various molecular visualization tools

## For more information
Do reach out to Correspondence: t.ibisanmi@unsw.edu.au (T.I.A.); n.kumar@unsw.edu.au (N.K.)
