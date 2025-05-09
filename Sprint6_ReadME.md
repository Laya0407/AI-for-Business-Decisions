# Sprint 6: GoodLife Fitness Club Analytics

## Project Overview
This project aims to optimize resource allocation at GoodLife Fitness, a leading fitness club chain in Canada. The analysis consists of two major components: 1) Class Attendance Prediction to optimize group fitness class utilization, and 2) Gym Occupancy Analysis to predict facility usage patterns for better resource management.

## Problem 1: Group Fitness Class Utilization

### Business Challenge
GoodLife Fitness experiences significant no-show rates for booked fitness classes, leading to underutilized resources and denied access to waitlisted members. This project develops a predictive model and overbooking strategy to optimize class capacity.

### Dataset Description
The dataset contains 1,500 class booking records with features including:
- Booking ID and member information
- Class details (category, day, time)
- Member attributes (months as member, weight)
- Booking behavior (days booked in advance)
- Attendance outcome (target variable)

### Methodology

#### Data Preprocessing
- Handled missing values in numerical columns using median imputation
- Standardized categorical variables (day names, time periods)
- Created derived features like membership tiers and recent booking indicators

#### Exploratory Data Analysis
Key findings:
- Overall attendance rate: 30.27%
- Attendance varies significantly by class category (Aqua: 32.9%, Strength: 26.6%)
- Day of week impacts attendance (Sunday: 33.3%, Wednesday: 20.7%)
- Strong relationship between membership tenure and attendance
- Morning classes show higher attendance (31.6%) than evening classes (26.2%)

#### Model Development
Implemented two predictive models:
1. **Random Forest Classifier**
   - Accuracy: 75.33%
   - Precision: 57.94%
   - Recall: 68.13%

2. **Gradient Boosting Classifier**
   - Accuracy: 78.00%
   - Precision: 64.37%
   - Recall: 61.54%
   - Selected as best model based on precision

#### Overbooking Strategy Development
- Created attendance tiers: Very Low (<20%), Low (20-25%), Below Average (25-30%), etc.
- Designed tiered overbooking ratios: 5.0x for Very Low, 3.5x for Low, 3.0x for Below Average, etc.
- Calculated recommended bookings for different class capacities
- Developed implementation phases for rollout

### Results and Recommendations

#### Class-Specific Overbooking Guidance
Overbooking recommendations by class type and time:
- Yoga-PM (19.23% attendance): Book up to 100 people for 20 capacity (5.0x ratio)
- Strength-PM (23.08% attendance): Book up to 70 people for 20 capacity (3.5x ratio)
- HIIT-AM (32.67% attendance): Book up to 50 people for 20 capacity (2.5x ratio)

#### Implementation Strategy
1. **Phase 1 (Weeks 1-2)**: Configure booking system with variable capacity limits
2. **Phase 2 (Weeks 3-6)**: Apply overbooking to lowest attendance classes only
3. **Phase 3 (Weeks 7-12)**: Extend strategy to all classes, implement cancellation incentives
4. **Phase 4 (Ongoing)**: Monthly review and refinement of overbooking ratios

#### Expected Impact
- Increased class utilization rates
- Improved member satisfaction through better class availability
- More efficient resource allocation
- Data-driven decision making for class scheduling

## Problem 2: Gym Equipment Utilization

### Business Challenge
GoodLife Fitness needs to predict the number of people in the gym at different times to optimize staffing, equipment availability, and resource allocation during peak and off-peak hours.

### Dataset Description
The dataset contains hourly gym occupancy data with features including:
- Timestamps and date information
- Number of people (target variable)
- Day of week, weekend status, holiday indicators
- Environmental factors (temperature)
- Semester status (relevant for university-area locations)

### Methodology

#### Data Preprocessing and Feature Engineering
- Converted timestamp data to appropriate datetime format
- Created cyclical time features (hour_sin, hour_cos, etc.)
- Developed time block categorization (morning, afternoon, evening, night)
- Generated interaction features (weekend_morning, weekday_rush)
- Created temperature categories and congestion indices

#### Exploratory Data Analysis
Key findings:
- Peak hours: 5-8 PM with nearly 50 people on average
- Monday, Wednesday, and Tuesday are busiest days (32-33 people avg)
- Weekends show significantly lower usage (22-23 people avg)
- February, September, and April show highest occupancy
- Weekday occupancy (31.6) much higher than weekend (22.8)

#### Model Development
Implemented three predictive models:
1. **XGBoost**
   - MAE: 6.43
   - RMSE: 9.40
   - R²: 0.8292
   - Best performing model

2. **LightGBM**
   - MAE: 6.57
   - RMSE: 9.47
   - R²: 0.8263

3. **Random Forest**
   - MAE: 7.32
   - RMSE: 10.84
   - R²: 0.7727

#### Time Series Analysis
- Performed seasonal decomposition to identify weekly patterns
- Tested for stationarity using Augmented Dickey-Fuller test
- Visualized autocorrelation to identify cyclical patterns
- Implemented ARIMA forecasting for future occupancy prediction

### Results and Recommendations

#### Staffing Optimization
- Schedule additional staff during peak hours (5-8 PM)
- Reduce staffing during consistently quiet times
- Increase staffing on busiest days (Monday and Wednesday)
- Anticipate higher demand during February and September

#### Member Experience Enhancements
- Promote off-peak hours for a less crowded experience
- Implement loyalty programs to incentivize attendance during quieter periods
- Create special events for typically low-traffic periods
- Develop a real-time occupancy tracker in the GoodLife app

#### Equipment Management
- Schedule maintenance during off-peak hours
- Optimize layout to distribute popular equipment throughout the gym
- Consider additional equipment for peak periods
- Implement time limits on popular equipment during rush hours

## Technologies Used
- Python (pandas, numpy, scikit-learn)
- Machine learning (XGBoost, LightGBM, RandomForest)
- Time series analysis (ARIMA, seasonal decomposition)
- Data visualization (matplotlib, seaborn)

## Future Work
- Incorporate external factors like weather and local events
- Develop an integrated dashboard for real-time decision support
- Implement automated staffing optimization system
- Create personalized member recommendations based on gym occupancy

## Team Members
- Motolani Akingbade
- Miracle Messiri
- Layanika Vinay Saravanan
