# California Housing Price Prediction

A beginner machine learning project where I practice regression by predicting median house values in California with scikit-learn.

I'm just starting out with ML, so this repo is part of my learning journey. Feedback and suggestions are welcome!

## What This Project Is About

The goal is to get hands-on practice with the basic ML workflow and to see how different regression models behave on the same data:

1. Load a dataset and put it into a pandas DataFrame
2. Split the data into training and test sets
3. Train several regression models
4. Score each model and compare the results

**Models tried:**

- Ridge Regression
- Linear Regression
- Lasso Regression
- Random Forest Regressor

## Dataset

I used scikit-learn's built-in California Housing dataset (1990 U.S. Census), loaded with `fetch_california_housing`.

- **Rows:** 20,640 block groups
- **Features:** 8 numeric columns
- **Target:** median house value, in units of $100,000

| Feature | Description |
|---|---|
| `MedInc` | Median income in block group |
| `HouseAge` | Median house age in block group |
| `AveRooms` | Average number of rooms per household |
| `AveBedrms` | Average number of bedrooms per household |
| `Population` | Block group population |
| `AveOccup` | Average number of household members |
| `Latitude` | Block group latitude |
| `Longitude` | Block group longitude |

## Results

R² scores from my notebook, measured on the **training** set:

| Model | Training R² (approx.) |
|---|---|
| Ridge | 0.61 |
| Linear Regression | 0.60 |
| Lasso | 0.28 |
| Random Forest | 0.97 |

> **Note:** These are training scores, so the Random Forest's 0.97 probably means it is overfitting. I plan to fix this by scoring on the test set (see below). Results also change slightly between runs because the train/test split isn't seeded yet.

## What I Learned So Far

- How to load a dataset and turn it into a pandas DataFrame
- How to separate features (`X`) from the target (`y`) and use `train_test_split`
- That the same `fit()` / `score()` pattern works across different scikit-learn models
- That Lasso scored much lower than Ridge and Linear Regression here, while Random Forest scored very high on the training data
- That a high training score alone doesn't mean a model is good

## Next Steps

- [ ] Evaluate models on the test set instead of the training set
- [ ] Set `random_state` so results are reproducible
- [ ] Try cross-validation
- [ ] Add feature scaling and hyperparameter tuning (`GridSearchCV`)
- [ ] Add plots: feature correlations, predicted vs. actual values
- [ ] Try other metrics such as MAE and RMSE



## Project Structure

```
.
├── housing.ipynb       # Main notebook
├── requirements.txt    # Python dependencies
└── README.md
```

## Tools Used

Python, pandas, NumPy, Matplotlib, scikit-learn, Jupyter
