# DATA-780-Final-Project-Repo
# Cross-Cancer Prediction of ERBB2 (HER2) Expression Using Machine Learning

This project investigates whether machine learning models trained on breast cancer genomic data can accurately predict ERBB2 (HER2) expression and generalize across different cancer types. Using datasets from The Cancer Genome Atlas (TCGA) via the UCSC Xena Browser, we evaluate how well DNA copy number alterations explain downstream gene expression and assess cross-cancer transferability.

## Background

ERBB2 (HER2) is a clinically significant oncogene whose amplification drives tumor progression in several cancers, most notably breast cancer. While HER2 status is commonly treated as a binary classification problem, this project models ERBB2 expression as a continuous variable, providing a more detailed representation of oncogenic activity.

## Objectives

- Predict ERBB2 expression using gene-level copy number alterations  
- Compare performance across multiple machine learning models  
- Evaluate model generalization across cancer types  
- Analyze whether genomic-expression relationships are conserved across cancers  

## Datasets

Data were obtained from the UCSC Xena Browser (TCGA):

- **Training dataset:**
  - Breast invasive carcinoma (BRCA)

- **Testing datasets:**
  - Ovarian serous cystadenocarcinoma (OV)
  - Uterine corpus endometrial carcinoma (UCEC)

### Data types:
- RNA-seq gene expression (log₂(x+1)-transformed RSEM normalized)
- Copy number alterations (GISTIC2 gene-level estimates)

## Models Used

- Ridge Regression  
- Elastic Net (with cross-validation)  
- Random Forest  
- Gradient Boosting  

## Evaluation Metrics

- R² (coefficient of determination)  
- RMSE (root mean squared error)  
- MAE (mean absolute error)  
- Pearson correlation (linear agreement)  
- Spearman correlation (rank-order preservation)  

## Key Results

- Non-linear models (Gradient Boosting, Random Forest) outperform linear models  
- Strong predictive performance on breast cancer (training domain)  
- Partial generalization observed across cancers:
  - Better transfer to endometrial cancer (UCEC)
  - Limited transfer to ovarian cancer (OV)
- Models retain correlation structure even when absolute prediction accuracy decreases  

##  Insights

- ERBB2 expression is influenced by complex, non-linear genomic relationships  
- Copy number alterations provide meaningful predictive signal  
- Cross-cancer generalization is dependent on tumor-specific biology  

## Future Work

- Extend framework to additional tumor-associated antigens  
- Incorporate multi-omic data (methylation, mutations, etc.)  
- Transition from regression to clinically relevant classification tasks (HER2 status)  
- Improve model generalization across diverse cancer types  

## Repository Structure

- `notebooks/` – Data analysis and modeling workflows  
- `data/` – Dataset references (not included if large)  
- `models/` – Trained models and outputs  
- `figures/` – Visualizations and plots  
- `README.md` – Project overview  

## 🧪 Technologies Used

- Python (pandas, numpy, scikit-learn)  
- Matplotlib / visualization tools  
- UCSC Xena / TCGA datasets  

---

This project demonstrates how machine learning can be applied to uncover biologically meaningful relationships between genomic alterations and gene expression, with implications for biomarker discovery and precision oncology.
