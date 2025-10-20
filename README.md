# AI-ML Assignment 2: Linear Regression - House Price Prediction

**Student Name:** [Your Name Here]

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