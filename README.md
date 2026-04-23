# Bengaluru House Price Prediction

A machine learning project that predicts house prices in Bengaluru using a Random Forest Regressor based on property features such as location, square footage, number of bathrooms, balconies, and BHK.

## Problem Statement
The goal of this project is to predict the price of a house in Bengaluru using real estate property details. This is a regression problem where the target is the house price.

## Dataset
This project uses the `Bengaluru_House_Data.csv` dataset.

Main columns in the dataset include:
- `area_type`
- `availability`
- `location`
- `size`
- `society`
- `total_sqft`
- `bath`
- `balcony`
- `price`

Target column:
- `price`

Final features used by the model are created after preprocessing and encoding.

## Steps Performed
1. Imported required libraries such as pandas, numpy, and scikit-learn.
2. Loaded the Bengaluru house price dataset.
3. Performed basic data cleaning:
   - Filled missing `location` values with `other`
   - Removed rows with missing `size`, `total_sqft`, and `bath`
4. Performed feature engineering:
   - Extracted `bhk` from the `size` column
   - Converted `total_sqft` into numeric form
   - Handled ranges like `2100 - 2850` by taking the average
5. Dropped unnecessary columns:
   - `size`
   - `society`
6. Removed unrealistic or noisy data:
   - Kept houses with `total_sqft > 300`
   - Filtered rows where `bhk <= bath + 2`
7. Reduced rare locations into a common `other` category.
8. Defined input features and target variable.
9. Applied one-hot encoding to categorical variables using `pd.get_dummies()`.
10. Filled remaining missing numeric values using column means.
11. Split the data into training and testing sets.
12. Trained a `RandomForestRegressor` model.
13. Evaluated the model using train and test score.
14. Built an interactive prediction function for custom house price prediction.

## Model Used
### Random Forest Regressor
The notebook uses:
- `RandomForestRegressor(n_estimators=100, random_state=42)`

## Results
Scores shown in the notebook:
- **Train Score:** 0.9428
- **Test Score:** 0.6078

Example prediction from the notebook:
- **Predicted Price:** 83.28 Lakhs

## Conclusion
This project demonstrates a practical house price prediction workflow using machine learning.

Key takeaways:
- Data cleaning and feature engineering are very important in real estate datasets.
- Handling inconsistent square-foot values and rare locations improves model usability.
- Random Forest performs well on training data and gives a moderate test score, showing decent predictive ability but also some overfitting.

## Project Structure
```text
house_price_pred/
├── .gitignore
├── README.md
├── requirements.txt
├── Bengaluru_House_Data.csv
└── house_price_predector.ipynb
```

## How to Run
1. Keep `Bengaluru_House_Data.csv` in the same folder as the notebook.
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Open `house_price_predector.ipynb` in Jupyter Notebook, VS Code, or Google Colab.
4. Run the notebook cells in order.

## GitHub Repository Description
Bengaluru house price prediction using Random Forest Regression, feature engineering, data cleaning, and interactive price prediction in Python.
