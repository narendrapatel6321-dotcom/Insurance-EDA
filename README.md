# Insurance Cost Prediction

## Overview

This notebook explores a dataset containing information about individuals and their medical insurance costs. The goal is to build a model that can predict medical insurance charges based on various features such as age, sex, BMI, number of children, smoking status, and region.

## Dataset

The dataset used in this notebook is `insurance.csv`, which contains the following columns:

- `age`: Age of the primary beneficiary
- `sex`: Gender of the beneficiary (male or female)
- `bmi`: Body Mass Index, providing an understanding of body weight relative to height
- `children`: Number of children covered by health insurance
- `smoker`: Smoking status (yes or no)
- `region`: The beneficiary's residential area in the US (northeast, southeast, southwest, northwest)
- `charges`: Individual medical costs billed by health insurance

## Notebook Structure

The notebook is structured as follows:

1.  **Importing Libraries**: Imports necessary libraries for data manipulation, visualization, and modeling.
2.  **Load the Dataset**: Loads the `insurance.csv` file into a pandas DataFrame and displays the first few rows.
3.  **Exploratory Data Analysis (EDA)**:
    - Checks the size of the dataset.
    - Checks for null values.
    - Displays information about the dataset (data types, non-null counts).
    - Shows descriptive statistics of the dataset.
    - Visualizes the distribution of numerical features (`age`, `bmi`, `children`, `charges`) using histograms.
    - Visualizes the counts of categorical features (`children`, `sex`, `smoker`) using countplots.
    - Visualizes the distribution of numerical features using boxplots to identify outliers.
    - Generates a heatmap to visualize the correlation between numerical features.
4.  **Data Cleaning and Preprocessing**:
    - Creates a copy of the original DataFrame.
    - Checks for and removes duplicate rows.
    - Checks for null values again after removing duplicates.
    - Checks data types.
    - Encodes the 'sex' column (male=0, female=1).
    - Encodes the 'smoker' column (yes=1, no=0).
    - Renames 'sex' to 'is_female' and 'smoker' to 'is_smoker'.
    - Performs one-hot encoding on the 'region' column.
    - Converts boolean columns resulting from one-hot encoding to integers.
5.  **Feature Engineering and Extraction**:
    - Visualizes the distribution of the 'bmi' column.
    - Creates a new categorical feature 'bmi_category' based on BMI values.
    - Performs one-hot encoding on the 'bmi_category' column.
    - Converts boolean columns resulting from one-hot encoding to integers.
    - Displays the columns of the cleaned DataFrame.
    - Performs Standard Scaling on numerical features ('age', 'bmi', 'children').
    - Calculates Pearson correlation between selected features and 'charges'.
    - Performs Chi-squared test for independence between categorical features and a binned 'charges' column to assess their relationship.
    - Creates a final DataFrame `final_df` with features selected based on correlation and chi-squared test results.
6.  **Model Training**:
    - Splits the data into training and testing sets (80% train, 20% test).
    - Initializes and trains a Linear Regression model on the training data.
7.  **Model Evaluation**:
    - Makes predictions on the test set.
    - Calculates and displays the adjusted R-squared score to evaluate the model's performance.

## Results

The Linear Regression model achieved an adjusted R-squared score of approximately 0.7988 on the test set, indicating that the selected features explain about 80% of the variance in the insurance charges.

## Dependencies

- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn
- scipy

## How to Run

1.  Ensure you have the necessary libraries installed (`pip install pandas numpy matplotlib seaborn scikit-learn scipy`).
2.  Download the `insurance.csv` dataset.
3.  Run the notebook cells sequentially in a Python environment (e.g., Google Colab, Jupyter Notebook).
