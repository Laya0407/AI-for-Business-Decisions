# Sprint 1: Supply Chain Delay Analysis

## Project Overview
This project analyzes a supply chain dataset containing over 15,500 orders to identify patterns and factors that contribute to delivery delays. The goal is to build a predictive model that can forecast potential delays, helping businesses optimize their supply chain operations.

## Dataset Description
The dataset contains 41 columns with information including:
- Order details (ID, date, status)
- Customer information (location, segment, etc.)
- Product information (category, price, discount)
- Shipping information (mode, date)
- Delay status (label: -1 for early, 0 for on-time, 1 for delayed)

## Methodology

### Data Preprocessing
- Handled missing values in both numerical and categorical fields
- Converted date columns to datetime format
- Combined early (-1) and on-time (0) deliveries into a single category (0)
- Applied capping to outliers rather than removing them

### Exploratory Data Analysis
Key findings:
- Strong correlations between sales metrics (sales, order amounts, sales per customer)
- Negative relationships between profit metrics and profit ratios
- Minimal impact of geographic factors on sales/profit performance
- Delay categories: 58% delayed (label 1), 42% on-time/early (label 0)

### Feature Engineering
- Created datetime features from order and shipping dates
- Applied one-hot encoding to categorical variables
- Used log transformation to reduce skewness in numerical features

### Model Development
Implemented multiple classification models:
1. **Random Forest Classifier** (basic version)
2. **Random Forest with SMOTE** (to handle class imbalance)
3. **XGBoost Classifier**

### Model Optimization
- Applied SMOTE (Synthetic Minority Over-sampling Technique) to address class imbalance
- Used GridSearchCV for hyperparameter tuning
- Optimized for balanced precision and recall

## Results and Findings

### Model Performance
- Best model: Random Forest with class balancing achieved 66% accuracy
- Precision: 0.72 for delayed delivery predictions
- Recall: 0.68 for delayed delivery predictions
- Strong ability to identify risk factors for delivery delays

### Key Delay Factors
- Large warehouse-to-home distance significantly increases delay probability
- Certain product categories have higher delay rates
- Orders with higher discounts show increased delay probability
- Specific shipping modes correlate with higher delay rates

### Business Implications
1. Consider proximity to warehouses when promising delivery dates
2. Adjust delivery expectations for high-risk product categories
3. Implement special handling for orders with large discounts
4. Optimize shipping mode selection based on delay risk analysis

## Technologies Used
- Python (pandas, numpy, scikit-learn)
- Data visualization (matplotlib, seaborn)
- Machine learning (RandomForest, XGBoost)
- Imbalanced-learn (SMOTE)

## Future Work
- Incorporate more advanced time-series features
- Test additional models like LightGBM and neural networks
- Develop a decision support system for real-time delay risk assessment
- Implement cost-based optimization for delay prevention strategies

## Team Members
- Motolani Akingbade
- Miracle Messiri
- Layanika Vinay Saravanan
