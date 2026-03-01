# Quantum-Inspired Feature Selection for Drug Discovery (Google Colab)

## Repository Contents
This repo contains the Google Colab notebook implementation for the internal assessment topic:

**Quantum-Inspired Optimization in Life Sciences: Enhancing Machine Learning for Biological Discovery**  
**Case Study:** Using a **Quantum-Inspired Genetic Algorithm (QIGA)** to optimize the **feature selection** process on a drug-discovery dataset, and benchmarking it against baseline ML models.

**Notebook:** `BDA.ipynb`

---

## What the Colab Notebook Does

### 1) Data Loading
- Loads a high-dimensional drug discovery dataset (molecular descriptors / fingerprints).
- Validates schema and separates features (`X`) and target labels (`y`).

### 2) Data Pre-processing
- Handles missing values (if any).
- Standardizes / normalizes features where required.
- Performs train-test split with fixed random seed for reproducibility.

### 3) Baseline Models
Trains baseline models using all features:
- **Random Forest**
- **XGBoost**

Evaluates baseline performance using:
- Accuracy
- Precision
- Recall
- F1-score
- ROC-AUC
- PR-AUC
- Confusion Matrix

### 4) Quantum-Inspired Genetic Algorithm (QIGA) Feature Selection
Implements a Quantum-Inspired Genetic Algorithm where:
- Each feature is encoded as a **q-bit probability amplitude**
- Measurement generates a binary mask (selected/not-selected)
- Fitness is computed using model performance (and optionally penalized by feature count)
- Rotation gate updates q-bits to guide convergence toward better solutions

**Outcome:** A reduced feature subset that improves model generalization and efficiency.

### 5) Comparative Evaluation: Baseline vs QIGA
The notebook compares baseline vs QIGA selected feature models and generates:
- Confusion matrix comparison
- ROC curve comparison
- Precision-Recall curve comparison
- Feature reduction pipeline visualization

---

## Outputs / Figures

The following figures are generated and/or included for report usage:

- `cm_baseline.png` — Confusion matrix (baseline)
- `cm_qiga.png` — Confusion matrix (QIGA)
- `roc_baseline_vs_qiga.png` — ROC curve comparison
- `pr_baseline_vs_qiga.png` — Precision-Recall comparison
- `feature_reduction_pipeline.png` — Feature selection workflow illustration

Recommended folder structure:
.
├── BDA.ipynb
├── figures/
│ ├── cm_baseline.png
│ ├── cm_qiga.png
│ ├── roc_baseline_vs_qiga.png
│ ├── pr_baseline_vs_qiga.png
│ └── feature_reduction_pipeline.png
└── reference.bib


---

## How to Run (Google Colab)

1. Open Google Colab  
2. Upload `BDA.ipynb` (or open from GitHub)
3. Run the notebook top-to-bottom (Runtime → Run all)

**Runtime Settings**
- Python 3
- GPU optional (not strictly required unless XGBoost training is heavy)

---

## Reproducibility
To ensure consistent results:
- Fixed `random_state` in train/test split and model initialization
- Same evaluation metrics and thresholding logic applied across baseline and QIGA

---

## Evaluation Metrics Used
- Accuracy
- Precision
- Recall
- F1-score
- ROC-AUC
- PR-AUC
- Confusion Matrix
- Execution Time (where applicable)

---

## Notes for Academic Submission
- The notebook is designed to directly support your 20–25 page LaTeX report.
- Generated figures are high-utility for the “Simulation & Results” section.
- Ensure `reference.bib` is included in repo and cited in the report.

---

## Academic Integrity
All algorithmic logic for QIGA and evaluation is implemented as original academic work. External libraries are used with proper attribution through citations.

---

## Author
Suyash Humne
Eshani Kane
Department of Information Technology  
K J Somaiya School of Engineering, Mumbai, India
