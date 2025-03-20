# Household-Energy-Usage-Forecast


This repository contains a time-series regression project for forecasting household power consumption. The project involves data understanding, exploration, preprocessing, feature engineering, model selection, hyperparameter tuning, evaluation, and prediction. It is structured as a VS Code notebook with multiple executable cells.

## Table of Contents

- [Project Overview](#project-overview)
- [Repository Structure](#repository-structure)
- [Installation and Requirements](#installation-and-requirements)
- [Usage](#usage)
- [Data Description](#data-description)
- [Project Cells Overview](#project-cells-overview)
- [License](#license)

## Project Overview

This project uses the "Household Power Consumption" dataset from the UCI Machine Learning Repository to predict the global active power consumption. The key steps include:
- **Data Understanding and Exploration:** Univariate and bivariate analysis, outlier detection, and correlation analysis.
- **Additional Preprocessing:** Calculating daily averages and peak hours.
- **Data Preprocessing for Modeling:** Handling missing values, scaling features, and selecting features (removing those with high correlation).
- **Model Selection and Training:** Building multiple regression models (Linear Regression, Random Forest, Gradient Boosting, Neural Network, and AdaBoost) with hyperparameter tuning.
- **Model Evaluation:** Evaluating model performance using RMSE, MAE, and R².
- **Prediction:** Saving the best-performing model to a pickle file and using it to predict on test data.

## Repository Structure

├── data/ │ └── household_power_consumption.txt # Dataset file (if not available, the code will download it) ├── models/ │ └── best_model.pkl # Best model saved after training ├── daily_average_global_active_power.csv # Daily average power consumption file ├── notebook.ipynb # VS Code notebook with all cells └── README.md # This file

bash
Copy
Edit

## Installation and Requirements

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/yourusername/household-power-forecast.git
   cd household-power-forecast
Set Up a Virtual Environment (Optional but Recommended):

bash
Copy
Edit
python -m venv env
source env/bin/activate  # On Windows, use `env\Scripts\activate`
Install Dependencies: Install the required Python libraries using pip:

bash
Copy
Edit
pip install pandas numpy matplotlib seaborn scikit-learn requests
Usage
Open the Project in VS Code:

Open the folder in VS Code.
Use the "Python: Select Interpreter" command to choose your environment.
Run the Notebook Cells: The project is divided into separate cells (using # %% markers) for:

Data Understanding and Exploration
Additional Preprocessing (Daily Averages & Peak Hours)
Data Preprocessing for Modeling and Feature Selection
Model Selection, Training, and Evaluation
Saving the Best Model and Making Predictions
Execute each cell in order. The best-performing model will be saved as best_model.pkl and used for predictions on the test data.

Data Description
Dataset: Household Power Consumption dataset
Source: UCI Machine Learning Repository
Attributes:
Date, Time (parsed into a DateTime feature)
Global_active_power (target variable)
Global_reactive_power, Voltage, Global_intensity
Sub_metering_1, Sub_metering_2, Sub_metering_3
Preprocessing: Missing values are filled using the median based on the data distribution.
Project Cells Overview
Cell 1: Data Understanding and Exploration
Loads the dataset, handles missing values, and performs univariate and bivariate analyses (including outlier detection and correlation heatmaps). Highly correlated features (correlation > 0.75) are identified for removal.

Cell 2: Additional Preprocessing – Daily Averages and Peak Hours
Computes daily average power consumption and identifies peak hours by grouping data. The daily average is saved as a CSV file.

Cell 3: Data Preprocessing for Modeling and Feature Selection
Selects and scales features for model training after removing highly correlated features.

Cell 4: Model Selection, Training, and Evaluation
Splits the dataset chronologically (80% training, 20% testing). Trains multiple regression models (including hyperparameter tuning using GridSearchCV) and evaluates their performance. The best model is selected based on RMSE.

Cell 5: Save the Best Model and Make Predictions
Saves the best model to a pickle file and demonstrates prediction on the test set using the loaded model.

