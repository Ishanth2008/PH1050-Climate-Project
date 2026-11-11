# PH1050 - Earth's Climate: Physics and Data-Driven Modelling

## 1. Project Overview

This project investigates the relationship between atmospheric CO2 emissions and global temperature changes using mathematical physics models and data-driven approaches.

The main objective is to understand how increasing carbon dioxide emissions contribute to global warming and to evaluate the ability of different mathematical models to describe and predict temperature anomalies.

The project is divided into three major components:

1. Physics-based modelling
2. Comparison with real climate data and statistical analysis
3. Data-driven modelling using historical temperature and emissions records

## 2. Project Objectives

- Develop a physics-based model to study global temperature evolution.
- Determine equilibrium temperature using the bisection method.
- Simulate the governing ordinary differential equation (ODE) using Euler and fourth-order Runge-Kutta (RK4) methods.
- Investigate numerical convergence and the effect of model parameters.
- Include CO2 forcing to simulate temperature changes over historical periods.
- Compare simulated temperature with observed temperature anomalies.
- Develop data-driven models using historical climate data.
- Compare baseline, linear regression and quadratic regression models.
- Evaluate model performance on unseen historical data.

## 3. Physics-Based Model

The physics-based model describes the evolution of global temperature using an energy-balance approach.

The model considers the balance between incoming solar radiation, outgoing thermal radiation and external forcing.

The numerical methods used include:

- Bisection method for finding equilibrium.
- Euler method for solving the ODE.
- Fourth-order Runge-Kutta (RK4) method for numerical simulation.
- Convergence analysis by studying error against step size.
- CO2 forcing to investigate historical warming.

## 4. Data and Statistical Analysis

The simulated temperature response is compared with observed global temperature anomalies.

The analysis includes:

- Comparison between simulated and observed temperature.
- Investigation of the difference between predicted and observed warming.
- Introduction of a scaling factor to account for model limitations.
- Residual analysis to examine the difference between simulation and observations.

## 5. Data-Driven Modelling

### 5.1 Objective

The data-driven model investigates the relationship between cumulative CO2 emissions and global temperature anomalies.

Historical temperature and emissions data are used to train regression models and evaluate their predictive performance on later observations.

### 5.2 Data Sources

The project uses the following datasets:

**Global Temperature Anomaly**
- Source: NASA GISS Surface Temperature Analysis (GISTEMP).
- Contains annual global temperature anomaly observations.
- File: Temperature_Anomaly_Data.csv

**Global Carbon Emissions**
- Source: Global Carbon Project.
- Contains historical global carbon emission information.
- File: Global_Carbon_Budget_2025_v1.xlsx

The original datasets are retained for reproducibility.

### 5.3 Data Processing

The following processing steps are performed:

1. Load the annual temperature anomaly dataset.
2. Load historical carbon emissions data.
3. Extract global annual emissions.
4. Calculate cumulative emissions over time.
5. Match temperature and emissions observations by year.
6. Prepare the combined dataset for regression analysis.

Cumulative emissions are calculated as:

E_cum(t) = sum of annual emissions from the starting year through year t.

### 5.4 Training and Testing

The available historical observations are divided into separate periods:

- Training: 1880–1965
- Validation: 1966–1980
- Testing: 1981–2024

The training data are used to fit the regression models.

The validation data are used to examine model performance before final evaluation.

The testing data are used to evaluate predictions on later observations that were not used for model fitting.

### 5.5 Models Implemented

**A. Baseline Model**

The baseline model predicts the mean temperature anomaly of the training dataset.

T_predicted = Mean(training temperature anomalies)

This provides a reference against which the regression models can be compared.

**B. Linear Regression**

The linear model assumes a linear relationship between cumulative emissions and temperature anomaly.

T = a + bE

Where:
- T represents temperature anomaly.
- E represents cumulative emissions.
- a represents the intercept.
- b represents the regression coefficient.

**C. Quadratic Regression**

The quadratic model considers a second-degree polynomial relationship.

T = a + bE + cE²

This model allows the relationship between cumulative emissions and temperature anomaly to be nonlinear.

### 5.6 Model Evaluation

Model performance is evaluated using Root Mean Square Error (RMSE).

RMSE = sqrt[sum((T_actual - T_predicted)²)/n]

A lower RMSE indicates better agreement between predicted and observed temperature anomalies.

The baseline, linear and quadratic models are compared using validation and testing datasets.

### 5.7 Extrapolation Analysis

An extrapolation test is performed by training models on earlier historical observations and evaluating their predictions on later years.

The predicted temperature anomalies are compared with actual observations.

This analysis helps investigate:

- Whether the linear model captures the warming trend.
- Whether the quadratic model improves predictive performance.
- Whether the baseline provides a useful reference.
- Whether the models generalise to later historical observations.
- How model complexity affects extrapolation accuracy.

## 6. Results and Visualisations

The data-driven analysis includes the following visualisations:

1. Cumulative CO2 emissions versus year.
2. Temperature anomaly versus cumulative emissions.
3. Comparison of linear and quadratic regression models.
4. Actual versus predicted temperature anomalies during the testing period.

Quantitative performance comparisons are presented using RMSE values.

## 7. Repository Structure

```
PH1050-Climate-Project/
│
├── README.md
│
├── data/
│   ├── Temperature_Anomaly_Data.csv
│   └── Global_Carbon_Budget_2025_v1.xlsx
│
├── data_driven_model/
│   ├── Data-Driven-Model.ipynb
│   └── results/
│       ├── cumulative_emissions.png
│       ├── model_comparison.png
│       ├── extrapolation_test.png
│       └── model_metrics.csv
│
├── physics_model/
│
└── requirements.txt
```

## 8. Software and Libraries

The project uses Python and scientific computing libraries.

- Python
- NumPy
- Pandas
- Matplotlib
- SciPy
- Jupyter Notebook

## 9. Running the Data-Driven Model

Clone the repository:

```bash
git clone YOUR_GITHUB_REPOSITORY_URL
```

Move into the project directory:

```bash
cd PH1050-Climate-Project
```

Install the required dependencies:

```bash
pip install -r requirements.txt
```

Open the notebook:

```bash
jupyter notebook
```

Run the cells in Data-Driven-Model.ipynb.

## 10. Limitations

- The data-driven model considers cumulative CO2 emissions as its main predictor.
- Other climate influences are not explicitly represented in the regression models.
- Historical relationships may not remain unchanged in future periods.
- Quadratic regression can overfit the training data and may perform poorly during extrapolation.
- Prediction accuracy depends on data quality and the selected training period.

Therefore, the regression models should be interpreted as simplified empirical models rather than complete physical descriptions of the climate system.

## 11. Conclusion

This project combines physical modelling and data-driven approaches to investigate global warming.

The physics-based model studies temperature evolution using energy-balance principles and numerical methods.

The data-driven model examines the historical relationship between cumulative carbon emissions and global temperature anomalies using baseline, linear and quadratic regression.

Comparing model predictions with actual observations provides insight into the strengths and limitations of different approaches to climate modelling.

## 12. Data References

1. NASA GISS Surface Temperature Analysis (GISTEMP): https://data.giss.nasa.gov/gistemp/
2. Global Carbon Project: https://globalcarbonproject.org/

## 13. Project Information

Course: PH1050

Project: Earth's Climate - Physics and Data-Driven Modelling

Institution: IIT Madras

Team Members: Add the names of all team members here.

Academic Project.
