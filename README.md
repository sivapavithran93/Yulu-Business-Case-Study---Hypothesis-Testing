# Yulu Business Case Study - Hypothesis Testing
<img src="https://indigoawards.s3.amazonaws.com/store/photo/23213/image/optimal-400f588e579fb603c8d214dcc48d63a7.jpg" width="1000" height="500"> 

## About 

Yulu is India’s leading micro-mobility service provider offering shared electric cycles for a smooth, affordable, and convenient daily commute. This case study investigates the factors affecting the demand for Yulu’s shared electric cycles, aiming to address recent revenue dips and optimize service delivery.

## Dataset Overview 

The dataset includes the following features:

- **datetime**: Date and time of the rental.
- **season**: Season of the year (1: Spring, 2: Summer, 3: Fall, 4: Winter).
- **holiday**: Indicator if the day is a holiday (1: Yes, 0: No).
- **workingday**: Indicator if the day is a working day (1: Yes, 0: No).
- **weather**: Weather condition (1: Clear, 2: Misty, 3: Light Snow/Rain, 4: Heavy Rain/Snow).
- **temp**: Temperature in Celsius.
- **atemp**: Feels-like temperature in Celsius.
- **humidity**: Humidity percentage.
- **windspeed**: Wind speed.
- **casual**: Count of casual users.
- **registered**: Count of registered users.
- **count**: Total rental bikes count.

## Insights 

- **Date Range**: January 1, 2011, to December 19, 2012.
- **Seasonal Distribution**: Most frequent season is Winter.
- **Holiday Impact**: Non-holidays are predominant with only 311 holiday entries.
- **Weather Conditions**: Clear or partly cloudy weather is most common.
- **Temperature**: Mean temperature is 20.23°C; "feels-like" temperature is 23.66°C.
- **Humidity**: Mean humidity is 61.89%.
- **Windspeed**: Average windspeed is 12.8 units.
- **Casual Rentals**: Mean count is around 36.
- **Registered Rentals**: Mean count is approximately 155.
- **Total Rentals**: Mean total rental count is 191.

## Analysis 

### Uni-Variate Analysis

- **Season**: Uniformly distributed across seasons.
- **Holiday**: Predominantly non-holidays (97% of data).
- **Working Day**: Majority of data falls on working days (68%).
- **Weather**: Clear or partly cloudy conditions are most frequent (66%).

### Bi-Variate Analysis

- **Seasonal Trends**: Highest rentals in Fall and Summer; lowest in Spring.
- **Holiday Effect**: Higher rentals on non-holidays.
- **Weather Influence**: Favorable weather correlates with higher rentals.

### Correlation Insights

- **Temperature**: Moderate correlation with casual rentals.
- **Humidity**: Negative correlation with both casual and registered rentals.
- **Rental Types**: Strong positive correlation between casual and registered rentals.
- **Total Rentals**: Highly correlated with registered rentals.

## Hypothesis Testing 

### 1. Significant difference between booking of electric cycles on Weekdays and Weekends
- **Null Hypothesis(H0):** There is **No Significant difference** between booking of electric cycles on Weekdays and Weekends.
- **Alternate Hypothesis(Ha):** There is **Significant difference** between booking of electric cycles on Weekdays and Weekends.
- Based on the results of the two-sample independent t-test, we found that there is **No significant difference** between the number of electric cycles rentals on weekdays and weekends. Specifically:
  - The **t-statistic was 1.21**, which indicates a moderate difference in electric cycles  rental numbers between weekdays and weekends, but not a large one.
  - The **p-value of 0.226** is greater than the common **significance level of 0.05**, which means the difference observed is likely due to random variation rather than a real, statistically significant difference.
  - Therefore, **we fail to reject the null hypothesis** 
  - Which means that there’s no substantial evidence to support the idea that the number of electric cycles rentals is different on weekdays versus weekends. 
  - In simple terms, it seems that bike rental demand does not vary significantly between weekdays and weekends.

### 2. Significant difference between booking of electric cycles on Regulardays and Holidays
- **Null Hypothesis(H0):** There is **No significant difference** in the number of cycles rented on regular days and holidays.
- **Alternate Hypothesis(Ha):** There is **significantly  different** average number of cycles rented on regular days and holidays.
- Result for Two-Sample Independent t-test for Regulardays vs Holidays:
    - t-statistics: -0.5626
    - P-value: 0.5737
    - Conclusion: Since the p-value (0.5737) is much greater than the significance level of 0.05, we fail to reject the null hypothesis.
    - There is no significant difference in the number of electric cycles rented on regular days vs holidays. 
    - This suggests that the booking behavior is not strongly influenced by whether it is a holiday or a regular day.
    - Since there’s no significant difference, other factors such as weather, local events, or promotions might play a more crucial role in affecting rental patterns, and could be explored further for optimization.

### 3. Significant difference in the number of cycles rented across the different seasons
- **Null Hypothesis(H0):** There is **No significant difference** in the number of cycles rented across the different seasons.
- **Alternate Hypothesis(Ha):** There is **significantly  different** average number of cycles rented compared to the others.
- **ANOVA Test:**
    - t-statistics: 236.95
    - p-value: 6.16×10−149
    - Conclusion: The p-value is extremely small (far less than the common significance level of 0.05), so we reject the null hypothesis. 
    - This indicates that there is a significant difference in the average number of cycles rented across the different seasons (Spring, Summer, Fall, Winter).
- **Kruskal-Wallis Test:**
    - t-statistics: 699.67
    - p-value: 2.48×10−151
    - Conclusion: Similar to the ANOVA test, the p-value is incredibly small, and we reject the null hypothesis. 
    - This test confirms that there is a significant difference in the average number of cycles rented among the seasons.

### 4. Significant difference in the number of cycles rented across the different Weather Conditions
- **Null Hypothesis(H0):** There is **No significant difference** in the number of cycles rented across the different weather.
- **Alternate Hypothesis(Ha):** There is **significantly  different** average number of cycles rented compared to the weather.
- **ANOVA Test for Different Weather Conditions:**
    - t-statistics: 65.53
    - p-value: 5.48×10−42
    - Conclusion: The extremely small p-value allows us to reject the null hypothesis. 
    - This suggests that the average number of cycles rented significantly differs across different weather conditions.
    - In other words, the weather plays an important role in determining the number of bikes rented.

  
- **Kruskal-Wallis Test for Different Weather Conditions:**
    - t-statistics: 205.00
    - p-value: 3.50×10−44
    - Conclusion: Again, the small p-value leads to rejection of the null hypothesis. 
    - This supports the finding from the ANOVA test that there is a significant difference in the number of cycles rented across different weather conditions.
    - Since Kruskal-Wallis is a non-parametric test, it suggests that even without assuming normality of the data, there are differences in the number of rentals based on weather.

### 5. Weather Dependency on Season
- **Null Hypothesis(H0):** **Weather is independent of the season**. There is no association between the two variables.
- **Alternate Hypothesis(Ha):** **Weather is dependent on the season.** There is an association between the two variables.
- **Result**:
    - Chi-Square Statistic: 49.16
    - p-value: 1.55 × 10-7
    - Degrees of Freedom: 9
    - Since the p-value is extremely small and less than the significance level (α = 0.05), we reject the null hypothesis.
    - This means that weather is dependent on the season, i.e., the weather conditions vary based on the season.
    - The findings suggest that the type of weather experienced is associated with the season. 
    - For example, certain weather conditions like heavy rain or snow are likely to occur during specific seasons (e.g., winter).
    - while clear or mild weather is more common during others (e.g., spring or summer).

## **Insights:**
- **Weekday vs Weekend:** 
    - No significant difference in rentals between weekdays and weekends, suggesting that demand is consistent throughout the week. 
    - Other factors like weather and local events may play a more significant role.
- **Regulardays vs Holidays:** 
    - No significant difference in rentals between Regulardays and Holidays, suggesting that demand is consistent throughout the week. 
    - Other factors like Festivals and Government holidays may play a more significant role.    
- **Seasonal Demand:** 
    - Significant variation in bike rentals across seasons. 
    - Spring and Summer see higher demand, while Fall and Winter have lower demand, highlighting the need for seasonal demand forecasting.
- **Weather Impact:** 
    - Clear weather drives higher demand, while rain and mist reduce rentals. 
    - Heavy rain has especially low demand, suggesting the need for weather-specific strategies.
- **Weather-Season Dependency:**
    - Weather conditions are tied to seasons, with certain conditions (e.g., rain or snow) occurring more frequently in specific seasons, aiding in demand prediction.

## Recommendations 

- **Weekday vs Weekend:** Focus on other factors like weather, holidays, or events to understand rental demand better.
- **Regulardays vs Holidays:** Focus on other factors like Festivals, holidays, or government holidays to understand rental demand better.
- **Seasonal Demand:** Implement seasonal forecasting and dynamic pricing to optimize bike availability and pricing during peak and off-peak seasons.
- **Weather Strategy:** Develop weather-responsive promotions (e.g., discounts on rainy days) and plan for low-demand conditions like heavy rain.
- **Optimize Operations:** Use weather-season dependency to plan fleet availability, maintenance schedules, and marketing campaigns.

## Project Report

- [Python Analysis Notebook](https://github.com/ssgalactic/yulu-hypothesis-testing-case-study/blob/main/path/to/your/python_analysis_notebook.ipynb)  
- [Detailed PDF Report](https://github.com/ssgalactic/yulu-hypothesis-testing-case-study/blob/main/path/to/your/detailed_pdf_report.pdf)


