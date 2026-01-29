# Sepsis Metabolite–Protein Network – SScore Prioritization Pipeline

R scripts for the downstream analysis in the manuscript  
"Integrative metabolite–protein interaction networks reveal novel pathways and biomarkers in sepsis"  
(BMC Infectious Diseases, revision).

## What the code does
- Prepares 2×2 tables for Fisher's exact test per DPClusO cluster
- Runs Fisher's test and collects p-values
- Computes Significance Score (SScore) = minimum FDR-adjusted p-value across clusters for each gene
- Generates ROC/AUC plot to select optimal density threshold (0.4)

## Requirements
R ≥ 4.0  
Packages: stringr (install if needed: `install.packages("stringr")`)

## How to run
1. Place your files in the working directory:
   - densXX.csv (DPClusO clusters, genes in column 5)
   - list_met_gene_finalXX.csv (known sepsis genes)
   - allnetclus.csv (full network genes)
2. Run in order:
   ```r
   source("scripts/01_prepare_fisher_tables.R")
   source("scripts/02_run_fisher_and_roc.R")
   source("scripts/03_compute_sscore.R")
