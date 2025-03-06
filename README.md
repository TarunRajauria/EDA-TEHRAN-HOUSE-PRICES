# Tehran House Prices Analysis

This project focuses on analyzing residential property prices in Tehran using a dataset scraped from the Divar site. The dataset includes features such as price (in USD and IRR), area, number of rooms, availability of parking, warehouse, elevator, and address. The goal is to explore housing market trends, perform data preprocessing, and build machine learning models to predict house prices.

---

## Dataset Overview

The dataset contains the following features:
- **Price (USD)**: Price of the property in US Dollars.
- **Price (IRR)**: Price of the property in Iranian Rials.
- **Area**: Total area of the property in square meters.
- **Room**: Number of rooms in the property.
- **Parking**: Availability of parking (Yes/No).
- **Warehouse**: Availability of a warehouse (Yes/No).
- **Elevator**: Availability of an elevator (Yes/No).
- **Address**: Location of the property.

The dataset has **3,479 entries** and **7 columns**. Some preprocessing steps were applied to handle missing values and transform categorical variables.

---

## Project Steps

1. **Data Preprocessing**:
   - Removed the `Price (IRR)` column to focus on USD prices.
   - Handled missing values in the `Area` and `Address` columns.
   - Grouped the `Address` column into 4 categories based on the average price of houses in each region:
     - **Group 0**: Cheapest houses (0-35% of data).
     - **Group 1**: Average houses (35-70% of data).
     - **Group 2**: Expensive houses (70-95% of data).
     - **Group 3**: Very expensive houses (95-100% of data).

2. **Exploratory Data Analysis (EDA)**:
   - Analyzed the distribution of categorical variables (e.g., rooms, parking, warehouse, elevator).
   - Visualized the distribution of continuous variables (e.g., area, price).
   - Performed bivariate analysis to understand relationships between variables (e.g., price vs. area, price vs. rooms).

3. **Machine Learning Models**:
   - Used **LabelEncoder** to transform categorical variables into numeric values.
   - Scaled the data using **StandardScaler**.
   - Split the data into training (70%) and testing (30%) sets.
   - Built and evaluated the following models:
     - **Linear Regression**: Achieved 66% accuracy with an MAE of 82,847.
     - **Decision Tree**: Achieved 81% accuracy with an MAE of 43,748.
     - **Random Forest**: Achieved 84% accuracy with an MAE of 43,726.

4. **Feature Importance**:
   - Identified the most important features for predicting house prices:
     - **Address Groups**: The most significant feature, contributing 83% to the model's predictions.
     - **Area**: The second most important feature, contributing 15%.

---

## Key Findings

- **Categorical Variables**:
  - Most houses have 2 rooms.
  - Over 80% of houses have parking, a warehouse, and an elevator.

- **Continuous Variables**:
  - Most houses have an area between 0-200 square meters.
  - Most houses are priced below $200,000.

- **Bivariate Analysis**:
  - Larger areas and more rooms generally lead to higher prices.
  - Houses with parking, warehouse, and elevator tend to be more expensive.

- **Machine Learning Results**:
  - The **Random Forest** model performed the best, with 84% accuracy and the lowest MAE.
  - The **address groups** (based on average price by region) were the most important feature for predicting house prices.

---

## Requirements

- Python 3.x
- Libraries:
  - `pandas`, `numpy`, `matplotlib`, `seaborn`, `plotly`
  - `scikit-learn`
  - `yellowbrick`

---

## Installation

1. Clone the repository or download the Python script.
2. Install the required libraries:

   ```bash
   pip install pandas numpy matplotlib seaborn plotly scikit-learn yellowbrick
