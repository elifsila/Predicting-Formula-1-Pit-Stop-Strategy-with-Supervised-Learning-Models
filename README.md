# F1 Strategy Dataset: Seven Kaggle Research-Question Notebooks

This ZIP contains seven independent Jupyter notebooks for the Kaggle dataset:
`aadigupta1601/f1-strategy-dataset-pit-stop-prediction`.

Each notebook answers one research question and saves:

- one or more publication-ready tables as `.csv`
- one publication-ready figure as `.pdf`

Outputs are written to an `outputs/` folder created automatically by each notebook.

## How to run on Kaggle

1. Open Kaggle and create a new notebook.
2. Click **Add Data**.
3. Search for and attach **F1 Strategy Dataset (Pit Stop Prediction)**, or upload the raw dataset file manually.
4. Upload one of the `.ipynb` files from this ZIP.
5. Run all cells.
6. Download outputs from the `outputs/` folder.

The notebooks automatically search for `.csv`, `.xlsx`, or `.xls` files in `/kaggle/input/`.

## Input columns expected

The notebooks expect the dataset to include the binary target column:

- `PitNextLap`

They are designed for the dataset version with columns such as:

- `Driver`
- `LapNumber`
- `Compound`
- `Stint`
- `TyreLife`
- `Position`
- `LapTime (s)`
- `Race`
- `Year`
- `LapTime_Delta`
- `Cumulative_Degradation`
- `PitStop`
- `PitNextLap`
- `RaceProgress`
- `Normalized_TyreLife`
- `Position_Change`

`PitStop` is excluded from model predictors to avoid leakage.

## Notebook list

1. `RQ1_Baseline_Predictability.ipynb`  
   Baseline models: Logistic Regression, Decision Tree, k-NN.

2. `RQ2_Advanced_Model_Comparison.ipynb`  
   Candidate models: Logistic Regression, Random Forest, XGBoost, Linear SVM.

3. `RQ3_Feature_Engineering_Impact.ipynb`  
   Compares basic, tyre, degradation, and full feature sets.

4. `RQ4_Feature_Importance.ipynb`  
   Computes permutation feature importance and saves top features.

5. `RQ5_Metric_Sensitivity.ipynb`  
   Ranks models across Accuracy, Precision, Recall, F1-score, and AUC.

6. `RQ6_Robustness_Generalization.ipynb`  
   Tests standard split, 5-fold CV, cross-race testing, and noisy data.

7. `RQ7_Strategic_Usefulness.ipynb`  
   Evaluates race-phase usefulness and produces final decision matrix.

## Dependencies

Kaggle normally includes all needed packages:

- pandas
- numpy
- matplotlib
- scikit-learn
- xgboost
- openpyxl, if using Excel input

If XGBoost is unavailable, the notebooks use a Random Forest fallback where needed.

## Output examples

Each notebook creates files such as:

- `outputs/RQ1_baseline_model_performance.csv`
- `outputs/RQ1_baseline_model_performance.pdf`
- `outputs/RQ4_feature_importance.csv`
- `outputs/RQ4_feature_importance.pdf`

## Notes

The numeric values in the output tables are actual model results produced when you run the notebooks on Kaggle. They may differ slightly depending on package versions and dataset version.
