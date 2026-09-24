# Credit Default Prediction — Thesis Code

A credit-scoring pipeline on the **Give Me Some Credit** dataset (~150k borrowers, ~6.7%
default rate). It compares three model families (Logistic Regression, Random Forest,
XGBoost) across three feature configurations, then calibrates probabilities and turns them
into cost-sensitive lending decisions.

## Folders
- `data/` — the raw dataset (`cs-training.csv`)
- `EDA/` — exploration (reads data only, writes nothing)
- `Fitting/` — split, feature building, model tuning, calibration
- `Scoring/` — thresholds, final test evaluation, subgroup analysis
- `artifacts/` — everything the notebooks produce (data splits, models, parameters, results)
  - `artifacts/report_outputs/` — thesis-ready tables and required figures exported by
    `Scoring/04_report_exports.ipynb`

## Setup
Requires Python 3.12. Install the dependencies:

```bash
pip install numpy==2.3.5 pandas==2.3.3 scipy==1.17.1 scikit-learn==1.7.2 \
            xgboost==3.2.0 joblib==1.5.3 matplotlib==3.10.8 pyarrow==24.0.0 betacal==1.1.0
```

## How to run
Open the project in Jupyter (`jupyter lab` or `jupyter notebook`) and run the notebooks
**top-to-bottom, in this order**:

1. `Fitting/01_split_and_preprocessing.ipynb`
2. `Fitting/02_build_feature_configs.ipynb`
3. `Fitting/03_model_tuning_and_selection.ipynb`  ← slowest (full hyper-parameter search)
4. `Fitting/04_calibration.ipynb`
5. `Scoring/01_threshold_optimization.ipynb`
6. `Scoring/02_test_evaluation.ipynb`
7. `Scoring/03_subgroup_analysis.ipynb`
8. `Scoring/04_report_exports.ipynb` — optional final report export (tables as CSV/Markdown,
   required figures as PNG)

Each step reads the artifacts written by the previous one, so the order matters. The four
`EDA/` notebooks are standalone exploration — run them any time; they don't affect the
pipeline.

> Tip: in Jupyter use **Kernel → Restart & Run All** on each notebook for a clean run.
> The `artifacts/` folder already contains a finished run, so the Scoring notebooks can be
> opened and read without re-running everything.
