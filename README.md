# Heart Attack Risk Predictor

This project explores supervised machine-learning models for classifying heart-disease outcomes from patient measurements. The analysis is presented in a Jupyter notebook and uses the dataset included in `data/`.

> **Disclaimer:** This is an educational machine-learning project, not a medical device or a substitute for professional medical advice, diagnosis, or treatment.

## Repository contents

- `Heart Attack Risk Predictor.ipynb` — data preparation, exploratory analysis, model training, tuning, and evaluation.
- `data/heart_statlog_cleveland_hungary_final.csv` — input dataset used by the notebook.
- `data/documentation.pdf` and `data/A database for using machine learning and data mining techniques for coronary artery disease diagnosis.pdf` — accompanying data documentation and reference.
- `ML_Presentation_Final.pptx` and `Final Project.pdf` — project presentation and report.

## Dataset

The CSV contains 11 predictor columns and a binary `target` column. The notebook renames these columns for analysis:

| CSV column | Notebook name |
| --- | --- |
| `age` | `age` |
| `sex` | `sex` |
| `chest pain type` | `chest_pain` |
| `resting bp s` | `resting_bp` |
| `cholesterol` | `cholesterol` |
| `fasting blood sugar` | `fasting_bs` |
| `resting ecg` | `ecg_resting` |
| `max heart rate` | `max_hr` |
| `exercise angina` | `exercise_angina` |
| `oldpeak` | `ecg_oldpeak` |
| `ST slope` | `ecg_slope` |
| `target` | `heart_disease` |

The notebook checks and visualizes the data, imputes zero values in resting blood pressure and cholesterol with their column means, then compares Random Forest and Gradient Boosting classifiers. It reports classification metrics, confusion matrices, cross-validation results, and feature importance.

## Run the notebook

Use Python 3 with Jupyter installed. From the repository root:

```bash
python -m pip install jupyter numpy pandas matplotlib seaborn scikit-learn bokeh pandas-bokeh neptune-client
jupyter notebook "Heart Attack Risk Predictor.ipynb"
```

Run the notebook cells in order. The notebook includes a Neptune experiment-logging cell; configure its credentials securely for your own account, or skip that cell if you do not use Neptune. Do not commit API keys or other credentials.

The notebook uses older scikit-learn parameter conventions. If the Random Forest grid search rejects `max_features='auto'`, replace that option with a supported value such as `'sqrt'`.
