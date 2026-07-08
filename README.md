# Medical Data Classification — IAU Project

Predicting critical oxygen saturation (SpO₂) levels from medical monitoring data using a Decision Tree (ID3) built from scratch, with full exploratory data analysis, preprocessing, and statistical validation.

**Course:** IAU (Inteligentná Analýza Údajov / Intelligent Data Analysis), FIIT STU Bratislava
**Author:** Vitalii Diurd

## Overview

This project builds an end-to-end pipeline for classifying medical oximetry readings — SpO₂, heart rate, blood pressure, and temperature — into risk categories. The work is split into three notebooks, each covering a distinct stage of the analysis:

| Notebook | Stage | Contents |
|---|---|---|
| `part1.ipynb` | **EDA & Preprocessing** | Data cleaning, exploratory analysis, feature scaling (StandardScaler, MinMaxScaler, PowerTransformer), Box-Cox transformation |
| `part2.ipynb` | **Statistical Analysis** | Hypothesis testing with the Mann-Whitney U test to validate feature significance across classes |
| `part3.ipynb` | **Model Training & Evaluation** | Decision Tree (ID3) implemented from scratch, trained and evaluated on the processed dataset, with experiment tracking via Weights & Biases |

## Results

- **86.65% accuracy** with a from-scratch ID3 Decision Tree classifier
- Statistically validated preprocessing choices using Mann-Whitney U testing
- Full experiment history and metrics tracked in [Weights & Biases](https://wandb.ai/)

## Dataset

The dataset consists of medical monitoring records (`data.csv`, `observation.csv`) with the following features:
- SpO₂ (blood oxygen saturation)
- Heart rate
- Blood pressure
- Temperature

Pre-split train/test sets are included (`x_train.csv`, `x_test.csv`, `y_train.csv`, `y_test.csv`) for reproducibility.

## How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/VitaliiDiurd/iau.git
   cd iau
   ```

2. Install dependencies:
   ```bash
   pip install pandas numpy scikit-learn scipy seaborn matplotlib statsmodels wandb jupyter
   ```

3. Run the notebooks in order:
   ```bash
   jupyter notebook part1.ipynb   # EDA & preprocessing
   jupyter notebook part2.ipynb   # Statistical testing
   jupyter notebook part3.ipynb   # ID3 model training & evaluation
   ```

   Each notebook can be run independently to inspect its stage, but the pipeline is designed to be followed in sequence (1 → 2 → 3).

## Tech Stack

- **Language:** Python
- **Data & ML:** Pandas, NumPy, Scikit-learn
- **Statistics:** SciPy, Statsmodels
- **Visualization:** Seaborn, Matplotlib
- **Experiment Tracking:** Weights & Biases

## Notes

- The ID3 decision tree is implemented manually (not via `sklearn.tree`) to demonstrate the underlying algorithm — splitting criteria, information gain, and recursive tree construction.
- Preprocessing choices (which scaler/transform to use per feature) were guided by distribution analysis in `part1.ipynb` and confirmed statistically in `part2.ipynb`.
