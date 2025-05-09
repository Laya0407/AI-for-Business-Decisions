# Sprint 2: Airbnb Decision Support System (DSS)

## Project Overview
This project develops a comprehensive Decision Support System (DSS) for Airbnb hosts, providing price predictions and time series forecasting to optimize pricing strategies and maximize revenue. The system analyzes historical booking data to identify patterns and trends, helping hosts make data-driven decisions.

## Dataset Description
The analysis is based on the Airbnb NYC 2019 dataset containing 48,895 listings with the following information:
- Listing details (ID, name, description)
- Host information (ID, name, listings count)
- Location data (neighborhood, latitude, longitude)
- Property attributes (room type, amenities)
- Pricing information
- Availability and review metrics

## Methodology

### Data Cleaning & Preprocessing
- Handled missing values in critical columns (host_name, last_review, reviews_per_month)
- Converted date fields to appropriate datetime format
- Removed listings with zero price
- Created targeted preprocessing pipeline for numerical and categorical features

### Exploratory Data Analysis
Key insights:
- Identified price distribution across neighborhoods and room types
- Analyzed the relationship between location and pricing
- Examined how host experience (listings count) affects pricing
- Determined the impact of reviews and ratings on listing performance

### Price Prediction Model
Built a Random Forest Regressor model to suggest optimal pricing:
- Feature selection based on correlation and business importance
- Train-test split (80%-20%) for model validation
- Hyperparameter tuning to optimize model performance
- Model evaluation using MAE (Mean Absolute Error)

### Time Series Analysis
- Aggregated reviews per day to analyze booking patterns
- Performed seasonal decomposition to identify weekly and monthly patterns
- Tested for stationarity using Augmented Dickey-Fuller (ADF) test
- Implemented ARIMA and SARIMA models for forecasting future demand

## Results and Findings

### Price Prediction
- Mean Absolute Error: $43.84
- Identified most influential factors in price determination:
  - Location (neighborhood_group)
  - Room type
  - Minimum nights
  - Reviews per month
  - Calculated host listings count

### Time Series Insights
- Observed exponential growth in Airbnb activity since 2018
- Identified significant spike in reviews in 2019 (600,000+ reviews per month)
- Discovered seasonal patterns that hosts can leverage for dynamic pricing
- Created Auto ARIMA model for forecasting future booking demand

### DSS Function Implementation
Created a practical price suggestion function that:
- Takes in listing details as input
- Processes input through the trained model
- Returns a suggested price based on comparable listings
- Provides confidence intervals for the price recommendation

## Application & Business Value

### For Hosts
- Optimal pricing recommendations based on property characteristics
- Demand forecasting to adjust pricing during peak/off-peak periods
- Competitive analysis relative to similar properties
- Revenue optimization strategies

### For Property Managers
- Portfolio-wide pricing strategy
- Seasonal adjustment recommendations
- Performance benchmarking across multiple properties
- Identification of investment opportunities

## Technologies Used
- Python (pandas, numpy, scikit-learn)
- Time series analysis (statsmodels, pmdarima)
- Machine learning (RandomForestRegressor)
- Data visualization (matplotlib, seaborn)

## Future Work
- Incorporate more external factors (events, holidays, local attractions)
- Develop a more sophisticated dynamic pricing algorithm
- Create a user-friendly web interface for the DSS
- Implement real-time market monitoring for continuous price optimization

## Team Members
- Motolani Akingbade
- Miracle Messiri
- Layanika Vinay Saravanan
