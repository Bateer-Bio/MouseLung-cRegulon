# cRegulon Analysis for Mouse Lung Single-Cell Multi-omics Data
This repository provides the workflow to apply **cRegulon** (Combinatorial Regulon) to mouse lung single-cell RNA-seq and ATAC-seq data. The method identifies transcription factor (TF) combinatorial modules as regulatory units underpinning cell type landscapes.

> **Reference Paper**:  
> Feng, Z., Chen, X., Duren, Z. et al. Modeling combinatorial regulation from single-cell multi-omics provides regulatory units underpinning cell type landscape using cRegulon. *Genome Biol* 26, 220 (2025)  
> [DOI: 10.1186/s13059-025-03680-w](https://doi.org/10.1186/s13059-025-03680-w)

---

## 1. Installation
Follow the official cRegulon installation guide:  
📦 [cRegulon GitHub Repository](https://github.com/SUwonglab/cRegulon)

```bash
wget https://github.com/SUwonglab/cRegulon/archive/master.zip
unzip master.zip
cd cRegulon-master
wget -O cRegulonData.tar.gz https://figshare.com/ndownloader/files/47503895
tar -xzvf cRegulonData.tar.gz

## 2. Data Preparation

## 3. Run cRegulon Pipeline
