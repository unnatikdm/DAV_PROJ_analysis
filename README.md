# Nifty 50 Stock Analysis 📊

## Project Overview
This repository contains a data analysis and stock prediction project focused on the Indian Nifty 50 index. It includes data cleaning, exploratory visualization, feature engineering, and a simple linear regression model for stock price prediction.

## What is included
- `data/cleaned_nifty50.csv`: Cleaned Nifty 50 historical stock dataset used for analysis and modeling.
- `data/metadata.json`: Metadata information for the dataset.
- `nifty50_analysis.ipynb`: Exploratory data analysis (EDA) notebook with data inspection, missing value checks, statistics, correlation analysis, and visualizations.
- `nifty50_prediction.ipynb`: Prediction notebook that trains a linear regression model for one stock and saves predicted closing prices.
- `pred.csv`: Model output file with predicted closing prices.
- `combine.py`: Script to merge actual stock data with predictions and export the combined dataset to `combined_data.csv`.
- `combined_data.csv`: Combined actual and predicted stock data produced by `combine.py`.
- `Untitled.ipynb`: Additional notebook file (unused or placeholder).

## Key Components

### Data Analysis
The `nifty50_analysis.ipynb` notebook performs:
- Data loading and type conversion
- Missing value analysis and visualization
- Summary statistics for numerical and categorical fields
- Correlation matrix visualization
- Histograms, boxplots, scatter plots, and pairplots
- Sector and ticker-level inspections

### Prediction Model
The `nifty50_prediction.ipynb` notebook includes:
- Loading the same cleaned dataset
- Filtering for a specific stock ticker (`ADANIENT.NS`)
- Feature engineering, including lagged closing prices and scaled volume
- Train/test split and linear regression model training
- Model evaluation using MSE and R²
- Saving predictions to `pred.csv`

### Combining Actual and Predicted Data
The `combine.py` script:
- Reads the cleaned actual stock data from `data/cleaned_nifty50.csv`
- Filters the dataset for the selected ticker (`ADANIENT.NS`)
- Reads prediction data from `pred.csv`
- Merges actual and predicted values by `Date`
- Writes the merged result to `combined_data.csv`

## Setup Instructions

### 1. Create a virtual environment
```bash
python3 -m venv .venv
source .venv/bin/activate
```

### 2. Install required packages
```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

> Note: If the notebooks install dependencies with `%pip install ...`, those packages may already be present in your environment.

## How to Use

### Run the analysis notebook
Open `nifty50_analysis.ipynb` in Jupyter or VS Code and execute the notebook cells sequentially to inspect data quality and visualize trends.

### Run the prediction notebook
Open `nifty50_prediction.ipynb`, execute the cells to train the linear regression model, and generate `pred.csv` with predicted closing prices.

### Combine actual and predicted values
```bash
python combine.py
```
This generates `combined_data.csv` by joining actual and predicted prices on the `Date` column.

## Expected Outputs
- `pred.csv`: Contains prediction dates and predicted closing values for the selected stock.
- `combined_data.csv`: Contains merged actual stock history and corresponding predictions.

## Dashboard Preview
The project also includes a dashboard-style summary visualization showing:
- Average daily return percentage and latest close value
- Yearly aggregated highs, lows, close sums, and trading volume
- Comparison of actual close values vs predicted close values

<img width="1107" height="613" alt="Screenshot 2026-04-23 234717" src="https://github.com/user-attachments/assets/dd87fe02-5786-4cad-b0b0-bc1341c0e8de" />

> Save the provided screenshot in the repository root as `dashboard_preview.png` to display it here.

## Useful Notes
- The model in the prediction notebook is a simple linear regression baseline.
- Predictions are generated for a single stock ticker: `ADANIENT.NS`.
- The notebooks are designed for experimentation and can be extended to other tickers or more advanced models.

## Suggested Improvements
- Add a `requirements.txt` or `environment.yml` for reproducible setup
- Extend prediction to multiple tickers or full Nifty 50 coverage
- Try more advanced time series models (e.g., ARIMA, LSTM, XGBoost)
- Add automated data validation and model performance tracking

## License
This repository does not include a license file. Add one if you plan to share or publish the project.



