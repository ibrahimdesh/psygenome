# psygenome
Binary Classification of Mental Health Disorders Using Machine Learning: A Comprehensive Analysis of the PsyGenome Dataset

# Binary Classification of Mental Health Disorders Using Machine Learning

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-1.0+-orange.svg)](https://scikit-learn.org/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

A comprehensive analysis of the PsyGenome-MentalHealth Dataset using machine learning techniques for binary classification of mental health disorders.

## 📋 Overview

Mental health disorders affect approximately 1 in 8 people globally, yet many remain undiagnosed. This project applies machine learning to multi-omics data (genomic markers, gene expression, and DNA methylation) to create an effective screening tool that distinguishes healthy individuals from those with mental health conditions.

### Key Achievements
- **91.7% Accuracy** with Support Vector Machine (SVM)
- **94.87% Recall** - identifying 94% of individuals with mental health issues
- **96.11% ROC-AUC** - near-perfect discrimination ability
- **Reduced feature space** from 84 to 61 features using ensemble feature selection

## 🎯 Problem Statement

The project addresses the diagnostic gap in mental health by:
- Creating a binary classification system (Healthy vs. Unhealthy)
- Handling high-dimensional genomic data with limited sample size
- Managing class imbalance (78% Unhealthy vs. 22% Healthy)
- Identifying the most relevant biomarkers for mental health screening

## 📊 Dataset

**PsyGenome-MentalHealth Dataset (PG-MHD)**
- 500 patient records
- 84 features across multiple domains:
  - **Demographics**: Age, Gender, Family History
  - **Genomic Markers**: 50 SNP variants
  - **Transcriptomic Markers**: 20 Gene Expression levels
  - **Epigenetic Markers**: 10 DNA Methylation levels

Original classes: Bipolar, Alzheimer's, Schizophrenia, Healthy

## 🔧 Methodology

### 1. Data Preprocessing
- Binary class transformation (Healthy vs. Unhealthy)
- SMOTE (Synthetic Minority Over-sampling Technique) for class imbalance
- Stratified train-test split (80/20)

### 2. Feature Selection
Ensemble approach combining:
- **Mutual Information**: Captures non-linear dependencies
- **L1-Regularized Logistic Regression (Lasso)**: Embedded feature selection
- **Recursive Feature Elimination (RFECV)**: Iterative feature removal
- **Union Strategy**: Preserves biomarkers identified by either method

Final feature set: **61 features** (35 SNPs, 18 gene expressions, 8 methylation sites)

### 3. Classification Models
Four algorithms benchmarked:
- Logistic Regression (baseline)
- Support Vector Machine (SVM) with RBF kernel ⭐ **Best performer**
- Random Forest
- Gradient Boosting Classifier

### 4. Evaluation Metrics
- Accuracy, Precision, Recall, F1-Score
- ROC-AUC Score
- Confusion Matrix

## 📈 Results

### Model Performance Comparison

| Model | Accuracy | Precision | Recall | F1-Score | ROC-AUC |
|-------|----------|-----------|--------|----------|---------|
| **SVM** | **91.72%** | **89.16%** | **94.87%** | **0.9193** | **0.9611** |
| Random Forest | 87.26% | 80.21% | 98.72% | 0.8851 | 0.9275 |
| Gradient Boosting | 86.62% | 80.65% | 96.15% | 0.8772 | 0.9120 |
| Logistic Regression | 67.52% | 66.27% | 70.51% | 0.6833 | 0.7629 |

### SVM Confusion Matrix
- **True Positives**: 74/78 (94.87% recall)
- **True Negatives**: 70/79 (88.61% specificity)
- **False Negatives**: 4
- **False Positives**: 9

## 🛠️ Installation

```bash
# Clone the repository
git clone https://github.com/yourusername/mental-health-classification.git
cd mental-health-classification

# Create virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

