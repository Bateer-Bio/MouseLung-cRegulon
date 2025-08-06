# cRegulon Analysis for Mouse Lung Single-Cell Multi-omics Data
This repository provides the workflow to apply **cRegulon** (Combinatorial Regulon) to mouse lung single-cell RNA-seq and ATAC-seq data. The method identifies transcription factor (TF) combinatorial modules as regulatory units underpinning cell type landscapes.

> **Reference Paper**:  
> Feng, Z., Chen, X., Duren, Z. et al. Modeling combinatorial regulation from single-cell multi-omics provides regulatory units underpinning cell type landscape using cRegulon. *Genome Biol* 26, 220 (2025)  
> [DOI: 10.1186/s13059-025-03680-w](https://doi.org/10.1186/s13059-025-03680-w)

---

## 1. Installation
Follow the official cRegulon installation guide:  
📦 [cRegulon GitHub Repository](https://github.com/SUwonglab/cRegulon)

```
wget https://github.com/SUwonglab/cRegulon/archive/master.zip
unzip master.zip
cd cRegulon-master
wget -O cRegulonData.tar.gz https://figshare.com/ndownloader/files/47503895
tar -xzvf cRegulonData.tar.gz
```

## 2. Data Preparation

## 3. Run cRegulon Pipeline
### Step 1: Preprocessing & Pseudo-bulk Generation
```
python3 cRegulon.py prep --name Lung \
  --rna ./example_data/Lung/scRNA/ \
  --rna_meta ./example_data/Lung/lung_scRNA_Cluster.txt \
  --atac ./example_data/Lung/scATAC/ \
  --atac_meta ./example_data/Lung/lung_scATAC_Cluster.txt \
  -g mouse
```

### Step 2: GRN Construction (Per Cluster)
```
for c in $(cat ./PseudoBulk/Lung_CellType.txt); do
  python3 cRegulon.py grn -n Lung -ct $c -g mm10 -p 12
done
```

### Step 3: Identify cRegulons
```
python3 cRegulon.py model -n Lung -mmin 4 -mmax 20
```
**Outputs*​​*: Results/Lung/ (TF modules, association matrices, annotated subnetworks)






