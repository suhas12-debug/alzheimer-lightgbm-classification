# 🧠 Alzheimer's Disease Classification using Multimodal LightGBM

[![Python 3.10+](https://img.shields.io/badge/python-3.10+-blue.svg)](https://www.python.org/downloads/)
[![LightGBM](https://img.shields.io/badge/Model-LightGBM-green.svg)](https://lightgbm.readthedocs.io/)
[![ADNI](https://img.shields.io/badge/Data-ADNI-orange.svg)](https://adni.loni.usc.edu/)

> **An advanced machine learning framework for three-class Alzheimer's disease classification (CN / MCI / AD) leveraging the synergy of Cognitive Scores and Structural MRI Biomarkers.**

---

## 📌 Project Overview

This repository implements a **Multimodal LightGBM Ensemble** designed to assist in the early detection and classification of Alzheimer's Disease. By combining structural MRI data (processed via FreeSurfer 7.x) with clinical cognitive assessments, the model achieves superior predictive performance compared to unimodal approaches.

### Key Features
- **Multimodal Fusion**: Integrates MRI biomarkers (Hippocampus, Entorhinal volumes) with cognitive scores (MMSE, ADAS13, CDRSB).
- **Ensemble Architecture**: Uses a weighted probability ensemble of specialized LightGBM classifiers.
- **Robust Preprocessing**: End-to-end pipeline from raw ADNI CSVs to analysis-ready data.
- **Explainable AI**: Integrated feature importance analysis to visualize clinical drivers of classification.

---

## 📂 Repository Structure

```bash
├── data/               # Data descriptions and acquisition instructions
├── models/             # Trained LightGBM models and scalers (.joblib)
├── notebooks/          # Step-by-step implementation notebooks
│   ├── 01_data_preprocessing.ipynb
│   ├── 02_model_training.ipynb
│   ├── 03_evaluation.ipynb
│   └── 04_inference.ipynb
├── results/            # Evaluation metrics and visualization figures
│   └── figures/        # ROC curves, PR curves, and Feature Importance
├── requirements.txt    # Project dependencies
└── README.md           # Project documentation
```

---

## 🚀 Getting Started

### 1. Prerequisites
Ensure you have Python 3.10+ installed. Clone the repository and install the required packages:

```bash
git clone https://github.com/suhas12-debug/alzheimer-lightgbm-classification.git
cd alzheimer-lightgbm-classification
pip install -r requirements.txt
```

### 2. Data Acquisition
Due to privacy restrictions, raw ADNI data is not included. 
1. Apply for access at [ADNI LONI](https://adni.loni.usc.edu/).
2. Download `ADNIMERGE.csv` and `UCSFFSX7.csv`.
3. Place them as instructed in `notebooks/01_data_preprocessing.ipynb`.

### 3. Running the Pipeline
Follow the notebooks in numerical order:
1. `01_data_preprocessing`: Merges and cleans the datasets.
2. `02_model_training`: Trains the cognitive and MRI LightGBM models.
3. `03_evaluation`: Evaluates performance and generates figures.
4. `04_inference`: Demonstrates how to use the saved models for new predictions.

---

## 📊 Results & Performance

The model demonstrates high sensitivity and specificity across all three classes. Detailed evaluation metrics and visualizations can be found in the `results/` directory.

| Metric | Cognitive Model | MRI Model | Ensemble |
| :--- | :---: | :---: | :---: |
| **Accuracy** | ~85% | ~78% | **~89%** |
| **ROC-AUC (AD)** | 0.94 | 0.88 | **0.96** |

### Sample Visualizations
- **ROC Curves**: Multi-class AUC performance.
- **Feature Importance**: Identifying key biomarkers (e.g., Hippocampus volume, ADAS13).

---

## 🎓 Acknowledgments
This research was conducted as part of a project at **KLE Technological University, Hubballi, India**. We thank the **Alzheimer's Disease Neuroimaging Initiative (ADNI)** for providing the dataset.

---
*Disclaimer: This tool is for research purposes only and should not be used for clinical diagnosis.*