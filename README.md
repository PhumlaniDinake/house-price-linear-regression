# House Price Prediction — Linear Regression

A multiple linear regression model that predicts house prices from area-level features, built in Python with scikit-learn.

Completed as a hands-on exercise in the CHPC (Centre for High Performance Computing) & NITheCS Coding Summer School, Week 2 (Machine Learning). The notebook follows course material that was adapted from a public tutorial ([github.com/tirthajyoti/Machine-Learning-with-Python](https://github.com/tirthajyoti/Machine-Learning-with-Python)).

## What the Notebook Covers

- Loading and inspecting the data (shape, data types, summary statistics)
- Exploratory visualisation: pair plots, price distribution, correlation matrix and heatmap
- Splitting the data into training (70%) and test (30%) sets, 3,500 and 1,500 rows, with a fixed random seed
- Fitting a multiple linear regression model and reading its intercept and coefficients
- Evaluating predictions on unseen data with R², MAE, MSE and RMSE, plus an actual-vs-predicted plot

## Dataset

`USA_Housing.csv` — 5,000 rows, provided with the course material.

- **Features:** Avg. Area Income, Avg. Area House Age, Avg. Area Number of Rooms, Avg. Area Number of Bedrooms, Area Population
- **Target:** Price (ranging from about $16,000 to $2.47M, with a mean of about $1.23M)
- The `Address` column is text and was left out of the model.

## Results

Evaluated on the 1,500 test rows the model had not seen:

| Metric | Result |
|---|---|
| R² (test) | 0.915 |
| R² (training) | 0.919 |
| Mean absolute error (MAE) | about $81,136 |
| Root mean square error (RMSE) | about $100,342 |

- The model explains about 91.5% of the variation in price on unseen data.
- The typical prediction error is about $81,000 on prices averaging about $1.23M, which is roughly 7%.
- Training and test R² are very close (0.919 and 0.915), which suggests the model is not overfitting.

## Notes

- The coefficients are in the original, unscaled units of each feature, so they should not be compared with each other to rank which feature matters most.
- This is a learning exercise with five features and a linear model. It is not a tool for valuing real properties.

## Tools Used

Python, Pandas, NumPy, Matplotlib, Seaborn, scikit-learn, Jupyter Notebook

## How to Run

```bash
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
jupyter notebook house_price_linear_regression.ipynb
```

Run it from this folder, because the notebook reads `USA_Housing.csv` using a relative path.

## Files

```
house-price-linear-regression/
├── README.md
├── house_price_linear_regression.ipynb
└── USA_Housing.csv
```
