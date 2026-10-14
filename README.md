# Gene Expression Analysis in Spinal Cord Injury

## Overview

This project explores gene expression patterns in spinal cord injury (SCI) samples using Python. It demonstrates a reproducible bioinformatics workflow, including data preparation, quality checks, exploratory statistics, dimensionality reduction, and visualization.

The analysis uses the publicly available **GSE151371** dataset from the NCBI Gene Expression Omnibus (GEO).

## Research Questions

- How do gene expression patterns vary across healthy controls, non-CNS trauma controls, and spinal cord injury samples?
- Can principal component analysis (PCA) help visualize similarities and differences between samples?
- Which genes show exploratory expression differences between SCI samples and healthy controls?

## Dataset

- **Dataset:** GSE151371
- **Source:** [NCBI Gene Expression Omnibus](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE151371)
- **Sample groups:** Healthy controls, non-CNS trauma controls, and spinal cord injury
- **Expected sample counts:** 10 healthy controls, 10 non-CNS trauma controls, and 38 SCI samples

The project uses the GEO-provided normalized, batch-corrected expression matrix. Please consult the original GEO record for the study design, sample descriptions, and data-processing details.

## Tools and Technologies

- Python
- pandas and NumPy
- SciPy
- Matplotlib and Seaborn
- scikit-learn
- Google Colab

## Workflow

1. Download the public expression matrix and sample metadata.
2. Clean the data and match expression-matrix sample names to GEO metadata.
3. Check sample counts, missing values, and gene identifiers.
4. Visualize expression distributions across samples.
5. Use PCA to explore sample-level expression patterns.
6. Perform exploratory gene-wise comparisons between SCI and healthy controls.
7. Apply Benjamini–Hochberg correction to p-values.
8. Generate a volcano plot and a gene-expression heatmap.
9. Export processed data, statistical tables, figures, and a project summary.

## Repository Structure

```text
spinal-cord-injury-gene-expression-analysis/
├── README.md
├── spinal_cord_injury_analysis.ipynb
└── results/
    ├── expression_distribution.png
    ├── pca_plot.png
    ├── volcano_SCI_vs_Healthy.png
    ├── top_genes_heatmap.png
    ├── differential_expression_SCI_vs_Healthy.csv
    ├── differential_expression_SCI_vs_Trauma.csv
    ├── sample_metadata.csv
    ├── quality_report.csv
    └── PROJECT_SUMMARY.md
```

*The repository structure above describes the intended deliverables. Include only files that have actually been generated and checked.*

## Statistical Approach

Exploratory differential expression comparisons use Welch's independent-samples t-test, followed by Benjamini–Hochberg false-discovery-rate correction.

The input is a normalized, batch-corrected expression matrix rather than raw RNA-seq counts. Therefore, these comparisons are exploratory and should not be interpreted as a definitive RNA-seq differential-expression analysis. A more rigorous analysis would use raw counts, appropriate quality-control procedures, and a suitable statistical model, such as DESeq2 or edgeR, when the required data are available.

## Results

The notebook generates PCA and expression-distribution plots, a volcano plot, a heatmap, and tables of exploratory statistical results.

**Numerical findings and biological interpretations should be added here only after the analysis has been successfully run and the results have been reviewed.** Statistical significance alone does not establish biological importance or causality.

## Limitations

- The analysis depends on the data processing performed by the original study.
- Normalized expression values are not a substitute for raw counts in a count-based RNA-seq model.
- Exploratory statistical associations do not establish causation.
- Findings require biological interpretation and independent validation.

## Reproducibility

The analysis notebook is designed to run in Google Colab. It downloads the public GEO files and performs the workflow in Python.

For reproducibility, consult the GEO accession above and review the code, sample-matching checks, and exported outputs.

## Disclaimer

This is an educational bioinformatics project. It is not intended for clinical diagnosis, treatment decisions, or medical use.

## Author

Hatice İLHAN

