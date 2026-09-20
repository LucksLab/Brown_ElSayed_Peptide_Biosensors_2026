# Brown_ElSayed_Peptide_Biosensors_2026

Repository for Brown_ElSayed_Peptide_Biosensors_2026

This repo contains python code and data files for analysis used in Brown and Clark-ElSayed et. al. "Design and characterization of peptide-responsive biosensors"

1. `Brown_ElSayed_Peptide_Biosensors_2026.ipynb` contains code for generating the heatmap panels contained in the paper figures.

## Downloading Files

Files can be downloaded manually or obtained by:

```
git clone https://github.com/LucksLab/Brown_ElSayed_Peptide_Biosensors_2026.git
```

## System Requirements

The python packages required for a Python 3 Jupyter Notebook are as follows

```
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
from matplotlib.colors import LinearSegmentedColormap
from pathlib import Path
import os
```

Reading the `.xlsx` tables also requires `openpyxl`. The figures are typeset in Arial; if Arial is not installed matplotlib will substitute a default sans-serif font and print a warning, but the plots are otherwise unchanged.

## Code Usage

### Figure Data

Summary data tables and analysis code for the peptide-responsive biosensor heatmap panels.

Each `.xlsx` file in this repository is the plotting summary table for a single manuscript panel — endpoint or dose-response averages condensed from the raw plate-reader traces. The raw traces themselves are distributed with the manuscript as Supplementary Excel files (`Figure_1_Data.xlsx`, `Figure_4_Data.xlsx`, `SI_Data_Compiled.xlsx`); every table here has been checked against the corresponding summary block in those workbooks.

The notebook regenerates five panels and nothing else. All remaining panels in the paper — dose-response curves, bar charts, schematics, and every supplementary figure — were produced outside this notebook.

| Notebook cell | Manuscript panel | Data file | Output SVG |
|---|---|---|---|
| 1 | Fig. 1c — ligand specificity | `Ligand_Specificity_Heatmap.xlsx` | `Ligand_Specificity_Heatmap.svg` |
| 2 | Fig. 1d — promoter specificity | `Promoter_Specificity_Heatmap.xlsx` | `Promoter_Specificity_Heatmap.svg` |
| 3 | Fig. 4a — alanine scan, cell-free translated | `WT_DNA_Alanine_Scan_Heatmap.xlsx` | `WT_DNA_Alanine_Scan_Heatmap.svg` |
| 4 | Fig. 4b — alanine scan, cellular translated | `Cellular_Alanine_Scan_Revised.xlsx` | `Ceullular_Arabinose_Alanine_Scan_Revised_Heatmap.svg` |
| 5 | Fig. 4d — SSM peptide variant dose-responses | `Cellular_Peptide_Variants_Combined.xlsx` | `Ceullular_Peptide_Variants_Medium_Combined.svg` |

## Data files

The following Excel files are used by `Brown_ElSayed_Peptide_Biosensors_2026.ipynb` and should be kept in the same directory as the notebook before running it:

- `Ligand_Specificity_Heatmap.xlsx`
- `Promoter_Specificity_Heatmap.xlsx`
- `WT_DNA_Alanine_Scan_Heatmap.xlsx`
- `Cellular_Alanine_Scan_Revised.xlsx`
- `Cellular_Peptide_Variants_Combined.xlsx`

### Table contents

**`Ligand_Specificity_Heatmap.xlsx`** — Fig. 1c. Five synthetic peptides (SHP2, SHP3, XIP-ST, XIP-SI, PapR) by five transcription factors (Rgg2, Rgg3, ComR-ST, ComR-SI, PlcR), each with a paired `Error` column. Endpoint (t = 600 min) sfGFP signal standardized to MEF (µM FITC); n = 3 experimental replicates. Cell-free reactions with 375 µM peptide, 50 nM reporter DNA, 9% (v/v) TF CFPS.

**`Promoter_Specificity_Heatmap.xlsx`** — Fig. 1d. Six reporter conditions by five transcription factors; averages only. Same units and conditions as Fig. 1c. Note that the row labels in this file were carried over from the ligand-specificity table; the six rows are in fact the promoters `pRgg2`, `pRgg3`, `pComR-ST`, `pComR-SI`, `pPlcR` and a no-peptide cognate-promoter control. The values are correct and match the supplementary workbook.

**`WT_DNA_Alanine_Scan_Heatmap.xlsx`** — Fig. 4a. Eleven SHP3 alanine-scan conditions with `Signal` and `Error` columns; fold activation normalized to 1, n = 3. Cell-free reactions with 50 nM reporter template, 80 nM peptide DNA, 9% (v/v) Rgg3 CFPS. Row labels `Ala1`–`Ala8` correspond to D2A, I3A, I4A, I5A, I6A, V7A, G8A and G9A; `D1R` is the D2R substitution.

**`Cellular_Alanine_Scan_Revised.xlsx`** — Fig. 4b. The same alanine-scan library expressed from pBAD in *E. coli* DH10B. Eleven rows by eight arabinose concentrations (`Conc 1`–`Conc 8` = 0, 0.0005, 0.001, 0.0025, 0.005, 0.05, 0.1, 0.2% w/v). Values are RFU/OD, n = 3 biological replicates. Rows include the wild-type circuit (`Rgg3 + SHP3`) and the peptide-only and TF-only controls.

**`Cellular_Peptide_Variants_Combined.xlsx`** — Fig. 4d. Twenty-eight rows by the same eight arabinose concentrations; RFU/OD, n = 3 biological replicates. Rows are three controls, twelve variants from the high-activity colony screen (D2R, D2A, I3L, I4T, I5V, I5L, I6L, V7T, G8T, G8H, G9M, G9I) and thirteen from the medium-activity screen (D2L, D2G, I3R, I3S, I4D, I4E, I5F, I5A, I6T, I6F, V7M, G8W, G9N).

## Usage

1. Download all five Excel files listed above, keeping their original file names.
2. Place them in the same directory as `Brown_ElSayed_Peptide_Biosensors_2026.ipynb`.
3. Run the notebook top to bottom. The first cell sets the working directory; all paths are relative, so no path editing is needed. Figures are written out as `.svg` files in the same directory.

Running this notebook should generate the output heatmap SVG files contained in Figures 1 and 4 of the manuscript.
