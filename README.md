# Cancer Mortality Rate Prediction Using Linear & Polynomial Regression

## Project Overview

This project applies **Linear Regression** and **Polynomial Regression** to predict cancer mortality rates across US counties using demographic, socioeconomic, and healthcare-related features.

The target variable is:

`TARGET_deathRate`

which represents the mean cancer mortality rate per 100,000 people.

## Objectives

* Explore the Cancer Mortality dataset
* Perform basic exploratory data analysis
* Check missing values and correlations
* Select relevant features and prepare the data
* Build a Multiple Linear Regression model
* Build Polynomial Regression models with degree 2 and degree 3
* Evaluate the models using MAE, MSE, RMSE, and R²
* Compare Linear and Polynomial Regression performance

## Dataset

The dataset contains **3,047 county-level records and 34 columns**.

The data includes variables related to:

* Cancer incidence and mortality
* Income
* Poverty
* Employment
* Education
* Health insurance coverage
* Demographic characteristics
* Population
* Birth rates

### Target Variable

`TARGET_deathRate`

## Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Scikit-learn
* Jupyter Notebook

## Project Workflow

```text
Dataset Loading
      ↓
Data Exploration
      ↓
Missing Value Analysis
      ↓
Distribution Analysis
      ↓
Correlation Analysis
      ↓
Feature Selection & Preprocessing
      ↓
Train-Test Split
      ↓
Multiple Linear Regression
      ↓
Polynomial Regression - Degree 2
      ↓
Polynomial Regression - Degree 3
      ↓
Model Evaluation
      ↓
Model Comparison
      ↓
Visualization
```

## Data Preprocessing

The dataset contains missing values in several numerical features.

Missing numerical values were handled using the **median** of the respective feature.

The following categorical columns were excluded from the regression features:

* `Geography`
* `binnedInc`

The target variable was separated as:

```python
y = TARGET_deathRate
```

and the remaining selected numerical variables were used as predictors.

## Train-Test Split

The dataset was divided into:

* **80% training data**
* **20% testing data**

A `random_state` of 42 was used to make the split reproducible.

## Models

### 1. Multiple Linear Regression

A Linear Regression model was trained using the selected numerical features.

### 2. Polynomial Regression - Degree 2

Polynomial features of degree 2 were generated and used with Linear Regression.

### 3. Polynomial Regression - Degree 3

Polynomial features of degree 3 were generated and used with Linear Regression.

## Model Evaluation

The models were evaluated using:

* Mean Absolute Error (MAE)
* Mean Squared Error (MSE)
* Root Mean Squared Error (RMSE)
* R² Score

### Results

| Model                          |   MAE |       MSE |   RMSE |        R² |
| ------------------------------ | ----: | --------: | -----: | --------: |
| Linear Regression              | 15.09 |    413.76 |  20.34 |    0.4943 |
| Polynomial Regression Degree 2 | 15.79 |    599.89 |  24.49 |    0.2669 |
| Polynomial Regression Degree 3 | 46.25 | 474242.55 | 688.65 | -578.5848 |

## Conclusion

Based on the test-set results, the **Multiple Linear Regression model performed better than both Polynomial Regression models** for this dataset.

Linear Regression achieved an MAE of approximately **15.09**, RMSE of approximately **20.34**, and an R² score of approximately **0.4943**.

Polynomial Regression with degree 2 did not improve the performance, while degree 3 produced substantially larger prediction errors and a strongly negative R² score on the test data.

Therefore, for this particular dataset and preprocessing approach, the linear model provided better test-set performance than the polynomial models evaluated.

## Visualizations

The project includes:

* Target variable distribution
* Actual vs Predicted values
* Residual plot

## Project Files

```text
cancer-mortality-regression/
│
├── data/
│   └── cancer_reg.csv
│
├── notebooks/
│   └── Cancer_Mortality_Regression.ipynb
│
├── images/
│   ├── target_distribution.png
│   ├── actual_vs_predicted.png
│   └── residual_plot.png
│
└── README.md
```

## Author

**Dilnaz Pathan**

Data Science / Machine Learning Project
