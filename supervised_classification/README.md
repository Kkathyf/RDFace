# Supervised Classification

This folder contains Jupyter notebooks for evaluating supervised phenotype classification performance using k-fold cross-validation. Each notebook explores different synthetic data augmentation strategies.

## Contents

| Notebook | Description |
|----------|-------------|
| `classification_kfold.ipynb` | Baseline classification using only real (non-synthetic) training data. |
| `classification_kfold_dream_topn.ipynb` | Classification with Top-n DreamBooth-generated synthetic images added to the training set. |
| `classification_kfold_fastgan_topn.ipynb` | Classification with Top-n FastGAN-generated synthetic images added to the training set. |

## Usage

1. Make sure dependencies (e.g., `scikit-learn`, `pandas`, `numpy`, `matplotlib`) are installed.
2. Open the notebook of interest and modify any dataset paths if needed.
3. Run all cells to train the classifier and generate performance metrics.

## Notes

- `topn` variants assume you have preselected the most realistic synthetic images and generated a csv file based on a defined metric (e.g., landmark similarity).
- All notebooks assume corresponding label metadata has already been generated for each dataset.
