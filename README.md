# scRNAseq Analysis: PARP Inhibitor Treatment in Mouse Breast Tumors

## Overview
This repository contains single-cell RNA sequencing (scRNAseq) analysis scripts examining tumor microenvironment composition and epithelial subpopulations across PARP inhibitor treatment phenotypes in a mouse breast cancer model.

## Treatment Phenotypes
| Short Code | Full Name     | Description                  |
|------------|---------------|------------------------------|
| PD         | Combo         | PARP inhibitor + combination |
| R          | PARPi_R       | PARP inhibitor resistant     |
| S          | PARPi_S       | PARP inhibitor sensitive     |
| DT         | PP2A          | PP2A treatment               |
| V          | Vehicle       | Vehicle control              |

## Analysis Scripts
| Script   | Description                                              |
|----------|----------------------------------------------------------|
| s1.Rmd   | Preprocessing, QC, normalization, and clustering         |
| s2.Rmd   | Lineage annotation and UMAP visualization                |
| s3.Rmd   | Epithelial subclustering and EGO enrichment analysis     |
| s4.Rmd   | HR module scoring and geneset analysis (MSigDB)          |
| s5.Rmd   | GSEA, cell type frequency, and visualization             |

## Sample Metadata
All samples are mouse breast tumors processed with 10x Genomics Single Cell 3' v3 chemistry, aligned to mm10-2020-A using CellRanger v6.0.2 with hashtag oligo (HTO) demultiplexing.

| Tumor ID  | Phenotype | Sequencing Run | Strategy      | ROCKi | Histology |
|-----------|-----------|----------------|---------------|-------|-----------|
| V3_T1     | Vehicle   | SCL210602RS    | MagCol        | No    | SP        |
| V3_T2     | Vehicle   | SCL210602RS    | MagCol        | No    | SP        |
| V4        | Vehicle   | SCL210602RS    | MagCol        | No    | SP        |
| S3        | PARPi_S   | SCL210602RS    | MagCol        | No    | SR        |
| V5        | Vehicle   | SCL210602RS    | FACS          | No    | SR        |
| R2        | PARPi_R   | SCL210602RS    | FACS          | No    | SP        |
| S4        | PARPi_S   | SCL210602RS    | FACS          | No    | SR        |
| V6_T1     | Vehicle   | SCL210816RS    | FACS          | No    | SR        |
| V6_T2     | Vehicle   | SCL210816RS    | FACS          | No    | SR        |
| V6_T3     | Vehicle   | SCL210816RS    | FACS          | No    | SR        |
| S6        | PARPi_S   | SCL210816RS    | FACS          | No    | SR        |
| S5        | PARPi_S   | SCL210816RS    | FACS          | No    | SR        |
| V7_T1     | Vehicle   | SCL210816RS    | MagCol_ROCKi  | Yes   | SR        |
| V7_T2     | Vehicle   | SCL210816RS    | MagCol_ROCKi  | Yes   | SR        |
| V7_T3     | Vehicle   | SCL210816RS    | MagCol_ROCKi  | Yes   | SR        |
| S7_T1     | PARPi_S   | SCL210816RS    | MagCol_ROCKi  | Yes   | SR        |
| S7_T2     | PARPi_S   | SCL210816RS    | MagCol_ROCKi  | Yes   | SR        |
| S8_T2     | PARPi_S   | SCL210922RS    | FACS_ROCKi    | Yes   | SR        |
| S8_T1     | PARPi_S   | SCL210922RS    | FACS_ROCKi    | Yes   | SR        |
| R6_T1     | PARPi_R   | SCL210922RS    | FACS_ROCKi    | Yes   | SR        |
| R6_T2     | PARPi_R   | SCL210922RS    | FACS_ROCKi    | Yes   | SR        |
| R4_T1     | PARPi_R   | SCL210922RS    | FACS_ROCKi    | Yes   | SP        |
| R4_T2     | PARPi_R   | SCL210922RS    | FACS_ROCKi    | Yes   | SP        |
| R4_T3     | PARPi_R   | SCL210922RS    | FACS_ROCKi    | Yes   | SR        |
| R5_T1     | PARPi_R   | SCL210922RS    | FACS_ROCKi    | Yes   | SP        |
| R5_T2     | PARPi_R   | SCL210922RS    | FACS_ROCKi    | Yes   | SR        |
| R5_T3     | PARPi_R   | SCL210922RS    | FACS_ROCKi    | Yes   | SR        |
| PD1_T1    | Combo     | SCL211020RS    | ROCKi         | Yes   | SR        |
| PD2_T1    | Combo     | SCL211020RS    | ROCKi         | Yes   | SP        |
| PD3_T1    | Combo     | SCL211020RS    | ROCKi         | Yes   | SR        |
| PD4_T1    | Combo     | SCL211020RS    | ROCKi         | Yes   | SR        |
| PD5_T1    | Combo     | SCL211020RS    | ROCKi         | Yes   |           |
| PD6_T1    | Combo     | SCL211020RS    | ROCKi         | Yes   |           |
| DT_T1     | PP2A      | SCL211208RS    | ROCKi         | Yes   | SP        |
| DT_T2     | PP2A      | SCL211208RS    | ROCKi         | Yes   | SR        |
| DT_T3     | PP2A      | SCL211208RS    | ROCKi         | Yes   | SR        |
| DT_T4     | PP2A      | SCL211208RS    | ROCKi         | Yes   | SR        |
| DT_T5     | PP2A      | SCL211208RS    | ROCKi         | Yes   | SR        |
| V8_T1     | Vehicle   | SCL211208RS    | ROCKi         | Yes   | SP        |

## Requirements
```r
# R >= 4.2
# Seurat v5
# Key packages:
install.packages(c("tidyverse", "ggpubr", "rstatix", "pheatmap", "plyr"))
BiocManager::install(c("fgsea", "msigdbr"))
```

## Key Parameters
- **Reference genome**: mm10-2020-A (mouse)
- **Chemistry**: 10x Genomics Single Cell 3' v3
- **CellRanger version**: 6.0.2
- **HTO demultiplexing**: TotalSeq-A/B hashtag oligos
- **Isolation strategies**: FACS, MagCol, MagCol+ROCKi, FACS+ROCKi

## Data Availability
Raw sequencing data available at GEO: [accession number to be added upon publication]

## Citation
[Citation to be added upon publication]
