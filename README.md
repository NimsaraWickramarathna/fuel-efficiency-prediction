# Fuel Efficiency Prediction Using Machine Learning

## Project Overview

This project is a beginner-friendly machine learning regression project that predicts a car's fuel efficiency using the **Auto MPG dataset**.

The target variable is **MPG (Miles Per Gallon)**. MPG shows how far a car can travel using one gallon of fuel. A higher MPG value means the car is more fuel efficient.

The main goal of this project is to build and compare machine learning models that can predict MPG using car-related features such as engine size, horsepower, weight, acceleration, model year, and origin.

This project follows a complete machine learning workflow:

1. Exploratory Data Analysis
2. Data Cleaning
3. Feature Engineering
4. Model Training
5. Model Evaluation
6. Model Comparison
7. Final Project Conclusion

---

## Problem Statement

Fuel efficiency is an important factor when comparing vehicles. Cars with better fuel efficiency consume less fuel and are more economical.

In this project, we use historical car data to predict a vehicle's fuel efficiency based on its technical specifications.

The machine learning problem is:

> Given a car's engine and vehicle details, predict its MPG value.

This is a **supervised machine learning regression problem** because the target value, MPG, is a continuous numerical value.

---

## Dataset Information

The dataset used in this project is the **Auto MPG dataset**.

The dataset contains information about different cars, including their engine specifications, weight, model year, origin, and fuel efficiency.

### Dataset Columns

| Column         | Description                                   |
| -------------- | --------------------------------------------- |
| `mpg`          | Miles per gallon. This is the target variable |
| `cylinders`    | Number of engine cylinders                    |
| `displacement` | Engine displacement                           |
| `horsepower`   | Engine horsepower                             |
| `weight`       | Vehicle weight                                |
| `acceleration` | Acceleration performance                      |
| `model_year`   | Year of the car model                         |
| `origin`       | Origin of the car                             |
| `car_name`     | Name of the car                               |

---

## Project Folder Structure

```text
fuel-efficiency-prediction-auto-mpg/
│
├── data/
│   ├── auto_mpg.csv
│   └── auto_mpg_cleaned.csv
│
├── notebooks/
│   ├── 01_eda.ipynb
│   ├── 02_data_cleaning.ipynb
│   └── 03_model_building.ipynb
│
├── src/
│   └── utils.py
│
├── requirements.txt
├── README.md
└── .gitignore
```

---

## File Descriptions

### `data/auto_mpg.csv`

This is the original raw dataset used for the project.

### `data/auto_mpg_cleaned.csv`

This is the cleaned dataset created after data preprocessing and feature engineering.

### `notebooks/01_eda.ipynb`

This notebook contains Exploratory Data Analysis.

Main tasks completed:

* Loaded the raw dataset
* Checked dataset shape
* Checked column names
* Checked data types
* Checked missing values
* Analyzed MPG distribution
* Analyzed relationships between MPG and other features
* Created visualizations
* Created correlation heatmap
* Identified important features for prediction

### `notebooks/02_data_cleaning.ipynb`

This notebook contains data cleaning and feature engineering.

Main tasks completed:

* Loaded the raw dataset
* Checked missing values
* Filled missing horsepower values using median
* Removed unnecessary `car_name` column
* Converted origin codes into readable region names
* Created new features
* Applied one-hot encoding
* Saved the cleaned dataset

### `notebooks/03_model_building.ipynb`

This notebook contains model training and evaluation.

Main tasks completed:

* Loaded the cleaned dataset
* Separated features and target variable
* Split data into training and testing sets
* Applied feature scaling
* Trained multiple regression models
* Evaluated models using R², RMSE, and MAE
* Compared model performance
* Visualized actual vs predicted values
* Created residual plot
* Checked feature importance
* Used cross validation

### `src/utils.py`

This file contains reusable helper functions for:

* Loading data
* Cleaning data
* Feature engineering
* Model evaluation
* Plotting actual vs predicted values
* Plotting residuals
* Comparing models

### `requirements.txt`

This file contains the required Python libraries for the project.

---

## Technologies Used

The following tools and libraries were used:

* Python
* Jupyter Notebook
* pandas
* numpy
* matplotlib
* seaborn
* scikit-learn
* VS Code
* GitHub

---

## Machine Learning Models Used

This project uses four regression models:

| Model                       | Purpose                                            |
| --------------------------- | -------------------------------------------------- |
| Linear Regression           | Simple baseline regression model                   |
| Decision Tree Regressor     | Tree-based model that captures non-linear patterns |
| Random Forest Regressor     | Ensemble model using many decision trees           |
| Gradient Boosting Regressor | Advanced ensemble model that improves step by step |

---

## Project Workflow

## 1. Exploratory Data Analysis

The first step was to understand the dataset.

EDA helped to answer questions such as:

* How many rows and columns are in the dataset?
* Are there missing values?
* What is the distribution of MPG?
* Which features have strong relationships with MPG?
* Which features may be useful for prediction?

Important findings from EDA:

* `mpg` is the target variable.
* `weight` has a strong relationship with MPG.
* `horsepower` and `displacement` affect MPG.
* Cars with fewer cylinders usually have higher MPG.
* Model year shows a trend in fuel efficiency.
* Origin may also influence fuel efficiency patterns.

---

## 2. Data Cleaning

The dataset was cleaned before training models.

Cleaning steps included:

* Checking missing values
* Handling missing values in `horsepower`
* Removing the `car_name` column
* Checking final dataset structure

The `car_name` column was removed because it is text data and may not be useful for a beginner-level regression model.

---

## 3. Feature Engineering

Feature engineering was used to create more useful input variables.

New features created:

| Feature                | Description                                |
| ---------------------- | ------------------------------------------ |
| `power_to_weight`      | Horsepower divided by weight               |
| `displacement_per_cyl` | Engine displacement per cylinder           |
| `is_v8`                | Identifies whether the car has 8 cylinders |
| `decade`               | Groups model years into decades            |

These new features can help the model understand vehicle performance and fuel efficiency better.

---

## 4. Encoding Categorical Data

The `origin` column was categorical.

Its original values were:

| Code | Origin |
| ---- | ------ |
| 1    | USA    |
| 2    | Europe |
| 3    | Japan  |

The origin values were converted into readable labels and then encoded using one-hot encoding so that machine learning models could use them.

---

## 5. Model Training

The cleaned dataset was split into:

* Training data: 80%
* Testing data: 20%

The training data was used to train the models, and the testing data was used to evaluate model performance.

Four models were trained:

1. Linear Regression
2. Decision Tree Regressor
3. Random Forest Regressor
4. Gradient Boosting Regressor

---

## 6. Model Evaluation

The models were evaluated using three regression metrics.

### R² Score

R² shows how well the model explains the variation in MPG.

* Higher R² is better.
* A value closer to 1 means better performance.

### RMSE

RMSE means Root Mean Squared Error.

* Lower RMSE is better.
* It shows the average prediction error with more penalty for large errors.

### MAE

MAE means Mean Absolute Error.

* Lower MAE is better.
* It shows the average absolute difference between actual MPG and predicted MPG.

---

## Model Comparison

After training all models, their performance was compared using R² Score, RMSE, and MAE.

The best model should have:

* Highest R² Score
* Lowest RMSE
* Lowest MAE

Tree-based ensemble models such as Random Forest and Gradient Boosting usually perform well because they can capture non-linear relationships in the dataset.

---

## Visualizations Included

This project includes several visualizations:

* MPG distribution plot
* Weight vs MPG scatter plot
* Horsepower vs MPG scatter plot
* Cylinders vs MPG boxplot
* Origin vs MPG boxplot
* Correlation heatmap
* Model year vs average MPG line plot
* Pairplot of important features
* Model comparison bar charts
* Actual vs predicted plot
* Residual plot
* Feature importance chart

These visualizations help to understand the data and model performance clearly.

---

## How to Run This Project

### Step 1: Clone the Repository

```bash
git clone https://github.com/your-username/fuel-efficiency-prediction-auto-mpg.git
```

### Step 2: Open the Project Folder

```bash
cd fuel-efficiency-prediction-auto-mpg
```

### Step 3: Create a Virtual Environment

```bash
python -m venv .venv
```

### Step 4: Activate the Virtual Environment

For Windows PowerShell:

```bash
.venv\Scripts\Activate
```

For Command Prompt:

```bash
.venv\Scripts\activate.bat
```

For macOS/Linux:

```bash
source .venv/bin/activate
```

### Step 5: Install Required Libraries

```bash
pip install -r requirements.txt
```

### Step 6: Install Jupyter Kernel

```bash
pip install ipykernel
```

```bash
python -m ipykernel install --user --name=fuel-efficiency --display-name "Python (Fuel Efficiency)"
```

### Step 7: Open Jupyter Notebook

```bash
jupyter notebook
```

Then run the notebooks in this order:

```text
notebooks/01_eda.ipynb
notebooks/02_data_cleaning.ipynb
notebooks/03_model_building.ipynb
```

---

## Requirements

The main required libraries are:

```text
jupyter
pandas
numpy
matplotlib
seaborn
scikit-learn
```

---

## Results Summary

The project successfully built a machine learning pipeline to predict car fuel efficiency.

Main results:

* The dataset was explored and understood using EDA.
* Missing values were handled.
* New useful features were created.
* Multiple regression models were trained.
* Model performance was evaluated and compared.
* The best model was selected based on evaluation metrics.

---

## Key Learnings

Through this project, I learned:

* How to load and explore a dataset
* How to check missing values
* How to clean data for machine learning
* How to create new features
* How to encode categorical variables
* How to split data into training and testing sets
* How to train regression models
* How to evaluate regression models
* How to compare model performance
* How to interpret feature importance

---

## Future Improvements

This project can be improved further by:

* Adding hyperparameter tuning
* Saving the best model using Pickle or Joblib
* Creating a Streamlit web app
* Adding user input prediction
* Improving feature selection
* Testing more regression models
* Deploying the project online

---

## Conclusion

This Fuel Efficiency Prediction project demonstrates a complete beginner-friendly machine learning workflow.

The project starts from raw data and continues through EDA, data cleaning, feature engineering, model training, and model evaluation.

It is a useful project for understanding regression problems and learning how machine learning can be used to predict real-world numerical values such as vehicle fuel efficiency.

---

