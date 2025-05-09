# Sprint 4: AI for Business Decisions - E-Commerce Churn Prediction

## Project Overview
This project develops a machine learning solution to predict customer churn for an e-commerce platform. By identifying customers at risk of leaving, businesses can implement targeted retention strategies to improve customer lifetime value and reduce customer acquisition costs. The analysis includes data cleaning, feature engineering, model development, and business recommendations.

## Dataset Description
The dataset contains 5,630 customer records with 20 features including:
- Customer demographics
- Purchase behavior
- Platform usage patterns
- Payment preferences
- Satisfaction metrics
- Churn status (target variable)

## Methodology

### Data Cleaning & Preprocessing
- Identified and handled missing values in numerical columns using median imputation
- Corrected inconsistent categories in categorical columns
- Visualized and handled outliers using capping method
- Applied Chi-square tests to examine relationships between categorical variables
- Used Cramér's V to measure the strength of association between categorical features

### Exploratory Data Analysis
Key insights:
- Found significant relationships between login device, gender, preferred order category, and marital status
- Analyzed customer distribution across different segments
- Identified demographic patterns related to churn behavior
- Discovered correlations between payment methods and customer retention

### Feature Engineering
Created new derived features to enhance model performance:
- **VisitFrequency**: Orders per unit tenure
- **AvgVisitGap**: Average time between visits
- **Recency**: Time since last order
- **OrderFrequency**: How often a customer places an order
- **DiscountUtilization**: How often coupons are used
- **EngagementScore**: Weighted sum of interactions
- **DormancyPeriod**: How long since last order relative to tenure

### Model Development
Implemented three classification algorithms:
1. **Logistic Regression**
   - Baseline model with interpretable coefficients
   - Achieved 90% accuracy, 75% precision, 58% recall

2. **Random Forest**
   - Ensemble method to capture complex relationships
   - Achieved 98% accuracy, 99% precision, 90% recall

3. **XGBoost**
   - Gradient boosting for optimal performance
   - Achieved 96% accuracy, 95% precision, 82% recall

### Model Optimization
- Used GridSearchCV for hyperparameter tuning
- Optimized XGBoost parameters: learning_rate=0.2, max_depth=7, n_estimators=100
- Final tuned model achieved 99% accuracy, 99% precision, 93% recall

## Results and Findings

### Model Performance
- Best model: Tuned XGBoost
- Accuracy: 99%
- Precision: 99%
- Recall: 93%
- AUC-ROC: 0.9983
- Very few false positives (1) and false negatives (13)

### Key Churn Factors (Feature Importance)
1. **Tenure**: Most critical factor, longer tenure correlates with lower churn
2. **Cashback Amount**: Higher cashback associates with greater loyalty
3. **Warehouse-to-Home Distance**: Delivery time influences retention
4. **Complain**: Customers who file complaints have higher churn risk
5. **Number of Addresses**: More addresses may indicate higher engagement
6. **Average Order Value**: Higher spending correlates with better retention

### Customer Segments
- Segmented customers into visit frequency categories:
  - Infrequent (46%)
  - Moderate (25%)
  - Frequent (22%)
- Found strong correlation between visit frequency and churn (0.38)

## Business Recommendations

### 1. Customer Retention Strategies
- Implement tenure-based loyalty rewards
- Develop special incentives for customers approaching churn risk thresholds
- Design targeted cashback promotions to keep users engaged

### 2. Customer Experience Improvements
- Prioritize complaint resolution process
- Reduce warehouse-to-home delivery times
- Create seamless multi-device experience

### 3. Marketing and Communication
- Develop re-engagement campaigns for inactive customers
- Analyze impact of price changes on customer behavior
- Create personalized communication based on engagement patterns

### 4. Product Development
- Focus on features that encourage frequent platform usage
- Implement real-time churn risk monitoring
- Develop early warning systems for at-risk customers

## Technologies Used
- Python (pandas, numpy, scikit-learn)
- Machine learning (XGBoost, RandomForest, LogisticRegression)
- Statistical analysis (Cramér's V, Chi-square)
- Data visualization (matplotlib, seaborn)

## Future Work
- Incorporate more advanced time-based features
- Develop a customer lifetime value prediction model
- Implement A/B testing framework for retention strategies
- Create a comprehensive customer segmentation system
- Develop an automated retention intervention pipeline

## Team Members
- Motolani Akingbade
- Miracle Messiri
- Layanika Vinay Saravanan
