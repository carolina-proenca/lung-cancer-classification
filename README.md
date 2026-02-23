# Pulmonary Nodule Classification (LIDC-IDRI)

**Malignancy Risk Assessment using Radiomics and Machine Learning**

Academic project for automated malignancy risk assessment of pulmonary nodules in CT scans using the public LIDC-IDRI dataset. This work integrates radiologist annotations, 2D/3D radiomics feature extraction, and machine learning models to classify nodules as benign or malignant.

> Note : Most of the documentation are in Portuguese, as this project was developed for the Laboratory of Artificial Intelligence and Data Science course (BSc in Artificial Intelligence and Data Science, University of Porto, 2025/2026).

## Authors

- Carolina Proença
- Eduarda Neves
- Elmano Vaz
- Maria Morais

## Objective

Develop a machine learning pipeline to classify pulmonary nodules as benign or malignant based on:
- Radiomics features (2D and 3D morphological and texture features)
- Patient information and nodule characteristics
- Multiple classification models with cross-validation

## Data

- **Source:** [LIDC-IDRI](https://www.cancerimagingarchive.net/collection/lidc-idri/) (The Cancer Imaging Archive)
- **Note:** The dataset is not included in this repository due to size constraints.

## Requirements

- **Python:** 3.10+ (tested with Conda/venv)
- **Core Libraries:** 
  - Data processing: pandas, numpy, scipy
  - ML/Analysis: scikit-learn, matplotlib, seaborn, tqdm
  - Medical imaging: pylidc, SimpleITK, pyradiomics
  - Notebook: jupyter

**Note:** GPU not required; CPU is sufficient for all experiments.

## Methodology & Results

### Feature Engineering
- **Feature Extraction:** 2D and 3D radiomic features extracted using PyRadiomics + SimpleITK over nodule masks from PyLIDC
- **Feature Selection:** ANOVA, LASSO, Random Forest importances, Spearman correlation analysis

### Model Development
- **Cross-validation:** Stratified group cross-validation by patient (leave-one-patient-out strategy)
- **Algorithms:** 
  - Logistic Regression
  - Support Vector Machine (SVM)
  - Random Forest (with probability calibration)
- **Evaluation Metrics:** AUROC, Average Precision, Brier Score, Precision, Recall, F1-score, Accuracy, ROC/PR curves, Confusion matrices

## Ethics & Legal Considerations

### Data Governance
- **Source:** Public, anonymized LIDC-IDRI dataset with consent collected at source
- **Compliance:** HIPAA de-identified data (no personally identifiable information)

### Responsible AI
- **Use Case:** Academic and research purposes only
- **Clinical Disclaimer:** This is not a clinical diagnostic tool and should not be used for patient diagnosis without proper medical supervision
- **Transparency:** All technical choices, preprocessing steps, and model parameters are fully documented
- **Reproducibility:** Controlled environment with version-controlled dependencies

### Limitations & Future Work
- **Data Bias:** Current dataset may have population bias; validation on more diverse cohorts recommended
- **Clinical Validation:** Real-world deployment requires clinical trials and regulatory approval
- **Model Improvement:** Future work includes ensemble methods, deep learning approaches, and multi-center validation

## Project Structure

```
Lung-Cancer-Classification/
├── Project_notebook.pdf                  # Work developed
├── LabIACD_20252026_project1.pdf         # Assignment 
├── consideraçoes_eticas_legais.pdf       # Ethical and Legal Considerations
└── README.md                             # This file
```

