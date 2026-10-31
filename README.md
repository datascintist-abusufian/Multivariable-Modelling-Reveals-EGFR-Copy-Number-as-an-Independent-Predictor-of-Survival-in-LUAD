# Multivariable Modelling Reveals EGFR Copy Number as an Independent Predictor of Survival in Lung Adenocarcinoma

Survival analysis code for a study of whether *EGFR* copy-number alteration (CNA) predicts overall survival in lung adenocarcinoma (LUAD) independently of clinical covariates. The analysis uses the TCGA LUAD PanCancer Atlas cohort.

## Data

- **Source:** TCGA Lung Adenocarcinoma (PanCancer Atlas), downloaded from [cBioPortal](https://www.cbioportal.org/).
- **In this repository:** `data_clinical_patient.txt` and `data_clinical_sample.txt` (public, de-identified TCGA clinical tables).
- **Not in this repository:** `data_cna.txt`, `data_mutations.txt` and `data_mrna_seq_v2_rsem.txt`. Download them from the same cBioPortal study and place them next to the notebook.

## Method

The notebook `Additional_Analysis.ipynb` runs the following steps:

1. Builds a modelling table that joins clinical variables with *EGFR* CNA status.
2. Fits a univariate Cox proportional-hazards model for each candidate variable.
3. Reports median overall survival by CNA group, with Kaplan-Meier curves and log-rank tests.
4. Fits a multivariable Cox model and draws a forest plot of hazard ratios.

Survival modelling uses [lifelines](https://lifelines.readthedocs.io/).

## Running it

```bash
pip install pandas numpy matplotlib lifelines
jupyter notebook Additional_Analysis.ipynb
```

The notebook was written in Google Colab and reads files from `/content/`. Change these paths to your local folder when running it elsewhere.

## Status

This is the analysis behind a manuscript in preparation. Results will be linked here once the paper is published.

## Licence

No licence has been declared yet. The TCGA data are subject to the [NCI Genomic Data Commons data-use policies](https://gdc.cancer.gov/access-data/data-access-processes-and-tools).

## Author

Md Abu Sufian - ORCID [0009-0007-3503-6942](https://orcid.org/0009-0007-3503-6942)
