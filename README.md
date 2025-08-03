# Spatial Transcriptomics of Breast Cancer Using 10x Visium

This project analyzes breast cancer tissue using **10x Genomics Visium spatial transcriptomics data**. Utilized the `Scanpy` Python framework to uncover spatial gene expression patterns, identify distinct tissue regions, and annotate cell types within the tumor microenvironment.

---

## Objectives

- Preprocess and filter spatial transcriptomics data
- Identify spatially variable gene expression patterns
- Cluster tissue spots and discover tumor subregions
- Annotate clusters with biologically meaningful cell types
- Visualize spatial architecture and gene markers in tissue

---

## Dataset

- **Source:** [10x Genomics Visium - Breast Cancer Block A, Section 1](https://www.10xgenomics.com/resources/datasets)
- **File Used:** `filtered_feature_bc_matrix.h5` (along with image and spatial metadata)

---

## Workflow Summary

### 1. Data Loading
Load the `.h5` expression matrix using `scanpy`.

### 2. Tissue Filtering
Keep only spots within tissue (`in_tissue == 1`) to exclude background noise.

### 3. Normalization & Log Transformation
Normalize total counts and apply log1p transformation for downstream analysis.

### 4. Highly Variable Genes
Select top 2,000 most variable genes using Seurat flavor.

### 5. Dimensionality Reduction
Apply PCA to compress data while retaining variance.

### 6. Neighborhood Graph
Construct a nearest-neighbors graph for clustering.

### 7. Clustering
Use the Leiden algorithm to identify transcriptionally distinct regions.

### 8. Marker Gene Ranking
Identify top genes distinguishing each cluster using Wilcoxon test.

### 9. Cell Type Annotation
Manually map clusters to known cell types using marker genes.

### 10. Visualization
Visualize annotated cell types in spatial tissue and UMAP plots.

---

## Example Outputs

- **Spatial plot of clusters:** Tissue sections colored by Leiden clusters.
- **UMAP:** Visualization of clusters in reduced 2D space.
- **Cell type map:** Tumor vs immune vs stromal regions annotated.
- **Top markers:** Genes characterizing each spatial domain.

---

## Tools & Libraries

- Python 3.11
- `scanpy`, `anndata`, `matplotlib`, `seaborn`
- 10x Genomics Visium data format

---

## Project Outcome

This analysis reveals spatial heterogeneity in breast cancer and helps map different cell types within tumor tissue. These insights contribute to understanding the tumor microenvironment, which is essential for precision oncology and biomarker discovery.

---

## Files

- `spatial transcriptomics.ipynb` – Main Jupyter Notebook with complete analysis
- `README.md` – This file

---

## 📎 License

This project is for educational and research purposes only.
