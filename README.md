# Car Price Prediction Project

## Project Overview

This project aims to build a **machine learning regression model** to predict car prices (MSRP) based on various vehicle characteristics. The project demonstrates a complete data science workflow from exploratory data analysis (EDA) through model development and evaluation.

## Problem Statement

**Objective:** Predict car prices (MSRP) based on vehicle attributes

**Problem Type:** Continuous Regression Problem
- Target variable: MSRP (continuous numerical value)
- Approach: Supervised learning with regression algorithms

## Dataset

**Source:** `archive/data.csv`

**Dataset Characteristics:**
- Contains vehicle specifications and pricing information
- Includes both categorical and numerical features
- 16 original features covering:
  - **Vehicle Info:** Make, Model, Year, Vehicle Size, Vehicle Style
  - **Engine Specs:** Engine Fuel Type, Engine HP, Engine Cylinders
  - **Performance:** Transmission Type, Driven Wheels, Highway MPG, City MPG
  - **Market:** Market Category, Popularity
  - **Target:** MSRP (Manufacturer's Suggested Retail Price)

**Sample Features:**
- BMW 1 Series M 2011: 335 HP, Premium Fuel, $46,135
- Luxury vehicles from multiple brands and years

## Project Structure

```
2_Lab/
├── README.md                    # Project documentation
├── archive/
│   └── data.csv                 # Raw dataset
├── Git/
│   └── Predict_car_prices.ipynb # Main analysis notebook
└── Manh_Seila_Group1_Week9.ipynb # Secondary notebook
```

## Methodology

### 1. **Data Import & Exploration (EDA)**
- Load dataset using pandas
- Inspect shape, data types, and basic statistics
- Analyze distribution and skewness of numerical features
- Examine categorical feature values

### 2. **Data Cleaning**
- **Missing Values:** 
  - Engine Fuel Type: Forward fill with mode
  - Engine HP: Fill with median
  - Engine Cylinders: Fill with median
- **Duplicate Records:** Remove exact duplicates
- **Final Validation:** Confirm no missing values remain

### 3. **Outlier Detection & Removal**
- **Method:** IQR (Interquartile Range)
  - Calculate Q1, Q3, IQR for each numeric column
  - Define bounds: [Q1 - 1.5×IQR, Q3 + 1.5×IQR]
  - Remove records outside bounds
- **Visualization:** Boxplots for outlier inspection

### 4. **Data Visualization**
- **Distributions:** Histograms for all numeric features
- **Correlation Analysis:** Heatmap showing feature correlations
- **Relationships:** Pair plots for multivariate analysis
- **Target Distribution:** KDE plot of MSRP

### 5. **Feature Engineering**
- **Encoding:** Convert categorical variables to numerical codes
  - Make, Model, Engine Fuel Type, Transmission Type, etc.
- **Data Preservation:** Save preprocessed data with pickle

### 6. **Data Splitting**
- **Training Set:** 70% of data
- **Validation Set:** 15% of data
- **Test Set:** 15% of data
- **Random State:** 42 (for reproducibility)

### 7. **Model Development**
- **Algorithm:** Linear Regression
- **Framework:** scikit-learn
- **Training:** Fit model on training data

### 8. **Model Evaluation**
Three-tier evaluation strategy using standard metrics:

| Metric | Formula | Interpretation |
|--------|---------|-----------------|
| MSE | Mean Squared Error | Lower is better |
| RMSE | √MSE | Root Mean Squared Error in dollar terms |
| R² Score | Coefficient of Determination | Higher is better (0-1 scale) |

**Evaluation Splits:**
- Training performance (model fit quality)
- Validation performance (generalization check)
- Test performance (final model assessment)

## Key Results

The notebook produces:
- Model performance metrics for all three datasets
- Performance comparison table (Train/Val/Test)
- Prediction vs. Actual distribution plots
- Identified important features

## Technologies & Libraries

```python
# Data Processing
pandas      # Data manipulation
numpy       # Numerical operations

# Visualization
matplotlib  # Basic plotting
seaborn     # Advanced statistical plots

# Machine Learning
scikit-learn  # Linear Regression & metrics
              # train_test_split
              # MSE, R² score calculation

# Serialization
pickle      # Data persistence
```

## Running the Project

### Prerequisites
```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

### Execution Steps
1. Open `Predict_car_prices.ipynb` in Jupyter Notebook or VS Code
2. Run cells sequentially from top to bottom
3. Each exercise (1-9) builds upon previous results

### Expected Outputs
- Data shape and statistics
- Outlier counts and removal results
- Categorical feature value counts
- Visualization plots (histograms, heatmaps, pair plots)
- Model performance metrics
- Prediction comparisons

## Data Processing Pipeline

```
Raw Data (data.csv)
    ↓
[Import & EDA]
    ↓
[Handle Missing Values]
    ↓
[Remove Duplicates]
    ↓
[Detect & Remove Outliers]
    ↓
[Feature Encoding]
    ↓
[Preprocessed Data]
    ↓
[Train/Val/Test Split]
    ↓
[Model Training & Evaluation]
    ↓
Results & Metrics
```

## Model Performance Assessment

The project evaluates whether:
- ✓ Training performance indicates model learning
- ✓ Validation performance detects overfitting
- ✓ Test performance confirms generalization
- ✓ R² score shows explanatory power
- ✓ RMSE is within acceptable range

## Notes for Future Enhancement

1. **Advanced Modeling:** Try additional algorithms (Random Forest, XGBoost)
2. **Feature Selection:** Identify most important features using correlation/importance scores
3. **Hyperparameter Tuning:** Optimize model parameters
4. **Cross-Validation:** Implement k-fold cross-validation
5. **Residual Analysis:** Analyze prediction errors
6. **Feature Scaling:** Normalize features if using distance-based algorithms

## File Descriptions

- **Predict_car_prices.ipynb:** Main project notebook with complete workflow
  - Exercises 1-9 covering problem definition through model evaluation
  - 40 code cells with detailed analysis
  - Inline visualizations and statistical summaries

- **data.csv:** Vehicle dataset
  - 16 features
  - Multiple vehicle makes and models
  - Year range: 1991-2017

- **preprocessed_data.pkl:** Serialized cleaned dataset
  - Generated after feature encoding
  - Ready for model training

## Authors & Context

- **Course:** Fundamental of Data Science - Week 9 Lab
- **Group:** Manh_Seila_Group1
- **Term:** Year 3, Term 2

## Summary

This project provides a complete walkthrough of the machine learning pipeline, from raw data to model evaluation. It demonstrates practical data preprocessing, exploratory analysis, and regression modeling techniques suitable for price prediction tasks.

---

**Last Updated:** March 2026
**Status:** Complete Educational Project
