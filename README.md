# 🧬 Differential Gene Expression Analysis (GSE19804)

An end-to-end bioinformatics pipeline in Python for identifying key biomarker candidates in paired **Lung Adenocarcinoma (LUAD)** vs. matched adjacent normal tissue samples from the NCBI GEO database (`GSE19804`).

---

## 📌 Project Overview
* **Dataset:** NCBI GEO [GSE19804](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE19804)
* **Sample Size:** 120 total samples (60 paired Tumor vs. 60 Normal)
* **Platform:** Affymetrix Human Genome U133 Plus 2.0 Array (GPL570)
* **Total Unique Genes Analyzed:** 23,520 genes

---

## 🔬 Methodology & Workflow
1. **Data Acquisition:** Downloaded and parsed GEO microarray expression data using `GEOparse`.
2. **Paired Analysis:** Performed paired t-tests (`scipy.stats.ttest_rel`) and calculated $\log_2$ Fold Change ($\log_2\text{FC}$) across patient-matched pairs.
3. **Multiple Testing Correction:** Adjusted p-values using the **Benjamini-Hochberg (FDR)** procedure (`statsmodels`).
4. **Probe Deduplication:** Mapped probe IDs to HGNC Gene Symbols, retaining the most statistically significant probe per gene.
5. **Dimensionality Reduction:** Evaluated global expression patterns across samples via **Principal Component Analysis (PCA)**.

---

## 🚀 Requirements
* Python 3.x
* `numpy`, `pandas`, `scipy`, `statsmodels`
* `matplotlib`, `seaborn`, `scikit-learn`
* `GEOparse`
