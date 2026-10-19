# House Price Prediction

This project analyzes residential sales data and builds a predictive model for house prices using Python notebooks, pandas, scikit-learn, and XGBoost. The workflow covers data cleaning, preprocessing, outlier treatment, exploratory analysis, feature engineering, and model evaluation.

## Project structure

- `datasets/` — source and processed datasets used by the notebooks
  - `housing.csv` — original raw dataset
  - `housing_no_missing_values.csv` — cleaned version after handling missing values
  - `housing_cleaned.csv` — processed dataset after outlier treatment
  - `housing_features_selected.csv` — feature-selected dataset used in the model notebook
  - `house_price_part1.csv` — additional housing-price data file used during exploration
- `notebooks/` — analysis and modeling notebooks
  - `House_Price_Prediction - Pre-processing_Missing_Values.ipynb`
  - `House_Price_Prediction - Pre-processing_Data-Formating.ipynb`
  - `House_Price_Prediction -Pre-processing_ handling_outliers.ipynb`
  - `House_Price_Prediction - data-Viz.ipynb`
  - `House Price Prediction - Feature Enginnering and Selection.ipynb`
  - `House_Price_prediction_Model_developpement.ipynb`
- `outputs/` — generated charts and model metrics
- `assets/` — supporting project images
- `requirements.txt` — Python dependencies for the project

## Environment setup

This project was developed with Python 3.12, as recorded in the notebook kernel metadata.

```bash
python -m venv .venv
source .venv/bin/activate   # Linux/macOS
.venv\Scripts\activate      # Windows
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
```

To run the notebooks:

```bash
jupyter notebook
```

## Data workflow

The project follows this pipeline:

1. Load the raw housing data from `datasets/housing.csv`
2. Clean missing values in `House_Price_Prediction - Pre-processing_Missing_Values.ipynb`
3. Standardize and clean the dataset in the formatting notebook
4. Handle outliers using winsorization/capping in the outlier-processing notebook
5. Explore patterns and relationships in the visualization notebook
6. Select relevant features before training the final model
7. Train and compare regression models in `House_Price_prediction_Model_developpement.ipynb`

The modeling notebook uses `SalePrice` as the target variable and reads the processed file `datasets/housing_features_selected.csv`.

## Model performance

The saved results in `outputs/performance_summary.csv` summarize the model evaluation. The recorded XGBoost comparison is shown below:

| Metric | Baseline XGBoost | Tuned XGBoost |
|---|---:|---:|
| Test R² | 0.8591 | 0.8800 |
| Test MAE | 19,200.00 | 18,201.30 |
| Test RMSE | 28,611.92 | 26,394.03 |

These are the project’s stored results; rerunning the notebooks may produce slightly different values depending on the exact data split and environment.

## Notes

- The repository includes the generated datasets, so you can run the notebooks directly after installing dependencies.
- If you want to reproduce the full preprocessing chain, run the notebooks in order from missing-value handling through model development.
- The output charts in `outputs/` can be used for quick visual validation of the analysis process.
