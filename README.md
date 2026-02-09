# psygenome
# Binary Classification of Mental Health Disorders Using Machine Learning
This repository contains the code and report for a machine learning system that applies binary classification algorithms to multi-omics data (genomic markers, gene expression, and DNA methylation) to distinguish healthy individuals from those with mental health disorders. The system combines ensemble feature selection with optimized classification models to support early screening and intervention in mental health care, achieving 91.7% accuracy and 94.87% recall.

The system features a **Dual-Stage Pipeline** that acts as an objective diagnostic support tool for healthcare providers:
1. **Feature Selection Engine:** Identifies 61 critical biomarkers from 84 multi-omics features using ensemble methods (Lasso + RFECV).
2. **Classification Model:** Predicts mental health status (Healthy vs. Unhealthy) using Support Vector Machine with RBF kernel for optimal precision-recall balance.

## 🚀 Key Features in the Three-Tier Architecture (Data, Model, and Evaluation)

* **Ensemble Feature Selection:** Union strategy combining L1-regularized regression (Lasso) and Recursive Feature Elimination (RFECV) to identify robust biomarkers.
* **Data Pipeline:** Comprehensive preprocessing handling binary transformation, class imbalance (SMOTE), and stratified splitting.
* **Multi-Algorithm Benchmarking:** Comparative analysis of Logistic Regression, SVM, Random Forest, and Gradient Boosting.
* **Clinical Metrics Dashboard:** Performance evaluation using Precision, Recall, F1-Score, ROC-AUC, and Confusion Matrix for medical decision support.
* **High-Dimensional Optimization:** Reduces feature space by 27% (84→61 features) while maintaining superior predictive power.

## 📊 Dataset & Performance

**PsyGenome-MentalHealth Dataset (PG-MHD)**
- 500 patient records with 84 features
- Multi-omics data: 50 SNP variants, 20 gene expressions, 10 methylation sites
- Binary classification: Healthy (109) vs. Unhealthy (391 aggregating Bipolar, Alzheimer's, Schizophrenia)

## 📖 Report
[Report]([https://drive.google.com/file/d/1fHUFmcecCSyo0XbT8o2PI0YPLSCKXRfe/view?usp=sharing](https://drive.google.com/file/d/1iCn0vURGf_b3USEd4B9A_yJzMMionPmD/view?usp=share_link))

## 🛠️ Installation & Usage

```bash
# Clone the repository
git clone https://github.com/yourusername/mental-health-classification.git
cd mental-health-classification

# Install dependencies
pip install -r requirements.txt

# Run the analysis pipeline
python main.py --data data/PsyGenome_dataset.csv --model svm

# Or explore via Jupyter notebooks
jupyter notebook notebooks/


