# AI-ML Assignment 2: Linear Regression - House Price Prediction

**Student Name:** Ermiyas H.

## Dataset
- **Source:** King County House Sales Dataset
- **Target Variable:** `price` (house sale price in dollars)
- **Original Size:** 21,613 houses
- **After Cleaning:** 21,598 houses (removed 15 outliers)

## Data Cleaning Steps
1. Loaded dataset using pandas
2. Checked for missing values (none found)
3. Identified and removed outliers:
   - Removed houses with unrealistic bedroom counts (>10 bedrooms)
   - Specifically removed 1 house with 33 bedrooms (data entry error)

## Feature Engineering
1. **Selected Feature:** `sqft_living` (square feet of living space)
   - Strong predictor of house price
   - Range: 290 - 13,540 square feet

2. **Created Feature:** `house_age` 
   - Formula: `2025 - yr_built`
   - Represents the age of the house in years
   - Range: 10 - 125 years

## Model Training
- **Algorithm:** Linear Regression
- **Train/Test Split:** 80% / 20% (17,278 training, 4,320 testing)
- **Model Equation:** `Price = 279.09 × sqft_living - 40,942.23`

## Evaluation Metrics (Test Set)
- **Mean Squared Error (MSE):** $67,137,959,511.78
- **R-squared (R²):** 0.5108

### Interpretation
- The model explains **51.08% of the variance** in house prices
- Average prediction error: approximately $259,110
- For a simple linear regression with one feature, this is a solid result
- The remaining 49% of variance is explained by other factors (location, condition, amenities, etc.)

## Visualization
Created a scatter plot showing:
- Blue dots: Actual house prices from test set
- Red line: Linear regression predictions
- Clear positive correlation between square footage and price

## Key Findings
- Every additional square foot of living space increases the predicted price by approximately $279
- Square footage alone accounts for about half of the price variation
- The model performs reasonably well for typical houses but may struggle with outliers

## How to run locally

If you'd like to reproduce or test the analysis on your machine, follow these steps.

1. Prerequisites
   - Python 3.8 or newer
   - Git (optional, to clone the repository)

2. Create and activate a virtual environment (recommended)

   macOS / Linux (zsh/bash):

   ```bash
   python3 -m venv .venv
   source .venv/bin/activate
   ```

3. Install minimal dependencies

   ```bash
   pip install --upgrade pip
   pip install pandas numpy scikit-learn matplotlib seaborn jupyter
   ```

4. Open and run the notebook
   - Start Jupyter Notebook or JupyterLab and open `AI-ML-Assignment-2-Linear-Regression.ipynb`.
   - Run the cells sequentially to reproduce the data loading, cleaning, feature engineering, model training, evaluation and plots.

   ```bash
   jupyter notebook AI-ML-Assignment-2-Linear-Regression.ipynb
   ```

5. Quick script run (optional)
   - If you prefer to run the analysis as a script, export the needed cells from the notebook to a `.py` file (Jupyter has `File -> Download as -> Python (.py)`) and run:

   ```bash
   python analysis.py
   ```

   - Note: the repository does not include an analysis script by default; the notebook is the primary artifact.

## Dataset notes
- The dataset file included in this repository is `kc_house_data_NaN.csv`.
- The notebook expects this CSV to be in the repository root (the same folder as the notebook). If you move the dataset, update the file path in the first notebook cell that loads the data.

## References
- https://www.kaggle.com/learn/intro-to-machine-learning
- https://www.kaggle.com/datasets/kamakshisoni/kchousedatanan?resource=download  — this is the exact information I used for the dataset
- https://www.kaggle.com/competitions/home-data-for-ml-course
- https://www.kaggle.com/competitions/house-prices-advanced-regression-techniques

## Notes
- If you hit missing-dependency errors, install the missing package with pip (for example `pip install package-name`).
- For reproducible results you can pin package versions (e.g., `pip freeze > requirements.txt`) and share the generated `requirements.txt`.