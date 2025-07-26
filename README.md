# PracticalApplication1-Will Customer Accept Coupon?

## Problem Statement
Once a specific coupon is delivered, what driver’s attributes, driving conditions, demographic factors, and coupon attributes most influence a driver's likelihood of accepting a specific coupon?

## Analysis Outline:
Data Description
Section 1. Data Review, Cleaning, and General Acceptance Rate Insights
Section 2.  Investigating the Bar Coupons
Section 3.  Independent Investigation – Other Attributes
Section 4.  Correlation Analysis
Section 5.  Next Steps and Recommendations

### The Jupyter Notebook link with full analyses: 

https://github.com/meiynajim/PracticalApplication1-CouponAcceptance/blob/main/CouponAcceptance.ipynb

## Executive Summary
Overall, these data analytics insights suggest that coupon acceptance is shaped by a combination of coupon attributes (type, time), contextual attributes (companions, time, weather, destination urgency), and user attributes (gender, age, marital status, education). The consistency between descriptive rates and inferential relationships strengthens confidence in these findings:

### Descriptive Analysis:

Coupon type Carry out & Take away has the highest acceptance rate = 73% vs Restaurant(<20) the 2nd highest =71% vs. Bar the lowest = 41%
Bar: Those who are more often to go to Bar have higher acceptance rate, 4-8 times has the highest rate 64%
For Bar-goers > 1/month, no kid passengers or age under 30 could have higher acceptance rate >=62%
Cheap restaurants-goers and low income acceptance rate = 60% (> average acceptance rate = 57%)
Destination No Urgent Place have the highest acceptance rate = 63% vs Work or Home rate only around 50%
Passanger Friend(s) has the highest acceptance rate = 67% vs Kid(s) lowest 50%
Weather Sunny has the highest acceptance rate = 59% (a little over average rate 57%) vs Rainy lowest 46%
Temperature 80 has the highest acceptance rate = 60% vs 30 53%
Time 2PM have the highest acceptance rate = 66% vs 10AM 61% as the second highest vs 7AM lowest 50%
Expiration in 1 day accpetance rate = 62% vs 2 hours is only 50%
Gender Male accpetance rate is 59% vs Female 55%
Age below 21 has the highest rate 63% vs. Age 50 puls lowest 51%: the higher age, the lower rate
Marital Status Single has the highest rate 60%, Unmarried partner 56% vs Widowed lowest 48%
Drivers no childrens rate is 59% higher than those with children 54%
Education with some high school has the highest rate 72% vs graduate degree 52%, the higher education, the lower rate
Occupation in Healthcare and Construction related has higher rate ~70% vs. Retired lowest 46%
CoffeeHouse 1~3 has the highest rate 65% vs never 46%
CarryAway greater than once has the highest rate 58%
Both RestaurantLessThan20 and Restaurant20To50 greater than 8 times has the highest rate 61% vs never around 52%
Not much difference in rate between same or opposite direction

### Correlation Analysis:

Features showed moderate positive correlation with coupon acceptance (Y), including: coupon_Carry out & Take away, coupon_Restaurant(<20), destination_No Urgent Place, expiration_2h, passanger_Friend(s), CoffeeHouse_never, toCoupon_GEQ25min, weather_Sunny, coupon_Coffee House, coupon_Restaurant(20-50)

Correlation between Destination No Urgent Place (acceptance rate = 63%) and Passanger Friend(s) (67%) shows high (0.6)

Statistical significance of these relationships implies non-random influence; Visualizations and grouped means (groupby().mean()) across categories confirmed patterns observed in descriptive stats and hinted at potential predictive variables.

e.g., When age is below21, the acceptance rate is highest 63%, the rate increasing with age decreasing, the younger age, more likely to accept.

## Section 1 Data Review, Cleaning, and General Acceptance Rate Insights
### Section Summary
##### Part 1 Data Review and Cleaning
 - **Data Before Cleaning: Rows = 12,684 rows | Columns =  26**
 - Identified 6 columns with missing: 
   - car: 12,576 missing - Action: dropped
   - Bar: 107 missing - Action: replaced by most frequent value(s)
   - CoffeeHouse: 217 missing - Action: replaced by most frequent value(s)
   - CarryAway: 151 - Action: replaced by most frequent value(s)
   - RestaurantLessThan20: 130 - Action: replaced by most frequent value(s)
   - Restaurant20To50: 189 - Action: replaced by most frequent value(s)
 - dentified 74 duplicated rows - Action: dropped
 - toCoupon_GEQ5min column only has one value which is 1 so not useful - Action: dropped
 - **Data After Cleaning: Rows = 12,610 | Columns = 24**

##### Part 2 General Acceptance Rate Insights

•	Overall, **57%** of the total observations chose to accept the coupon

•	Coupon Type Comparison: Carry out & Take away has the highest acceptance rate = 73% vs Restaurant(<20) the 2nd highest =71% vs. Bar the lowest = 41%


•	Acceptance by Temperature

![image.png](attachment:f76e0772-5c6e-42ed-a1b4-0e6ed6f9b2dc.png)


## Section 2 Investigating the Bar Coupons

### Section Summary

 - Coupon type `Carry out & Take away` has the highest acceptance rate = 73% vs `Restaurant(<20)` =71% vs. `Bar` lowest = 41%
 - For Bar-goers > 1/month, no kid passengers or age under 30 could have higher acceptance rate >=62% & Cheap restaurants-goers and low income acceptance rate = 60% (higher than average acceptance rate = 57%)


## Section 3 Independent Investigation - Other Attributes

Using the bar coupon example as motivation, you are to explore one of the other coupon groups and try to determine the characteristics of passengers who accept the coupons. 

### Section Summary
 - **Destination** `No Urgent Place` have the highest acceptance rate = 63% vs `Work` or `Home` rate only around 50%
 - **Passanger** `Friend(s)` has the highest acceptance rate = 67% than others
 - **Weather** `Sunny` has the highest acceptance rate = 59% (a little over average rate 57%) than others
 - **Temperature** `80` has the highest acceptance rate = 60% than others
 - **Time** `2PM` have the highest acceptance rate = 66% vs `10AM` 61% as the second highest
 - **Expiration** in `1 day` accpetance rate = 62% vs `2 hours` is only 50%
 - **Gender** `Male` accpetance rate is 59% vs Female 55%
 - **Age** `below 21` has the highest rate 63% vs. Age `50 puls` lowest 51%: higher age, lower rate
 - **Marital Status** `Single` has the highest rate 60%, `Unmarried partner` 56% vs `Widowed` lowest 48%
 - **Drivers** `no childrens` rate is 59% higher than those `with children` 54%
 - **Education** with `some high school` has the highest rate 72% vs `graduate degree` 52%, the higher education, the lower rate
 - **Occupation** in `Healthcare` and `Construction` related has higher rate ~70% vs. `Retired` lowest 46%
 - **CoffeeHouse** `1~3` has the highest rate 65% vs `never` 46%
 - **CarryAway** `greater than once` has the highest rate 58%
 - Both **RestaurantLessThan20** and **Restaurant20To50** greater than 8 times has the highest rate 61% vs never around 52%
 - Not much difference in rate between same or opposite direction

## Section 4 Correlation Analysis

### Section Summary
- Features showed moderate positive correlation with coupon acceptance (Y), including:
   `coupon_Carry out & Take away`, `coupon_Restaurant(<20)`, `destination_No Urgent Place`, `expiration_2h`, `passanger_Friend(s)`,
   `CoffeeHouse_never`, `toCoupon_GEQ25min`, `weather_Sunny`, `coupon_Coffee House`, `coupon_Restaurant(20-50)`
- Correlation between **Destination** `No Urgent Place` (acceptance rate = 63%) and **Passanger** `Friend(s)` (67%) shows high (0.6)

- Statistical significance of these relationships implies non-random influence; Visualizations and grouped means (groupby().mean()) across categories confirmed patterns observed in descriptive stats and hinted at potential predictive variables.
   - e.g., When age is ‘below21’, the acceptance rate is highest 63%, the rate increases with age decreasing, the younger age, more likely to accept.


## Section 5 Next Steps and Recommendations

**1. Data Expansion:** Investigate outliers, duplicates, and potential sampling biases

**2. Multicollinearity Review:** Use techniques like PCA or VIF to manage highly correlated features

**3. Feature Engineering:** Create meaningful features, composite features, and/or interaction terms.

  - e.g.: Consider combining variables like Destination + Passanger or Coupon Type + Time into interaction terms. Their joint effect seems significant based on this analysis.

**4. Feature Selection:** Rank feature importance via statistical or model-based methods

**5. Predictive Modeling:** Train models using logistic regression, decision trees, or ensemble methods to predict coupon acceptance with the main impactful variables which could be used to verify hypotheses around variable impact

**6. Model Optimization:** model tuning, testing, and validation to ensure generalizability



## Find a Bug?
If you found an issue or would like to submit an improvement to this project, please submit an issue using the issues tab above. If you would like to submit a PR with a fix, reference the issue you created. 

## Known Issues (Work in progress)
This project is still ongoing…
