# PracticalApplication1-CouponAcceptance

# Project: Will Customer Accept Coupon?
## Problem Statement
Once a specific coupon is delivered, what driver’s attributes, driving conditions, demographic factors, and coupon attributes most influence a driver's likelihood of accepting a specific coupon?
## Analysis Outline:
Section 1. Data Review, Cleaning, and General Acceptance Rate Insights
Section 2.  Investigating the Bar Coupons
Section 3.  Independent Investigation – Other Attributes
Section 4.  Correlation Analysis
Section 5.  Next Steps and Recommendations

## Part 1. Data Review, Cleaning, and General Acceptance Rate Insights
### Data Review and Cleaning:
•	The Raw Data: Rows = 12,684 rows | Columns =  26
•	Identified 6 columns with missing: 
       - car: 12,576 missing  dropped
       - Bar: 107 missing  replaced by most frequent value
       - CoffeeHouse: 217 missing  replaced by most frequent value
       - CarryAway: 151 missing  replaced by most frequent value
       - RestaurantLessThan20: 130 missing  replaced by most frequent value
       - Restaurant20To50: 189 missing  replaced by most frequent value
•	Identified 74 duplicated rows  removed
•	toCoupon_GEQ5min contains only one unique value   dropped
•	Data After Cleaning: Rows = 12,610 | Columns = 24

### General Acceptance Rate Insights:
•	Overall, 57% of the total observations chose to accept the coupon

•	Coupon Type Comparison
 ![image.png](attachment:e27fba10-459a-4d5a-b88b-5869c38dad92.png)

•	Acceptance by Temperature
 ![image.png](attachment:f76e0772-5c6e-42ed-a1b4-0e6ed6f9b2dc.png)
## Part 2. Investigating the Bar Coupons
•	Total bar coupons: 2,010
•	Acceptance rate for bar coupons: 41%
Key Subgroup Comparisons:
•	Drivers going to bars:
o	≤ 3 times/month → 56%
o	3 times/month → 62%
•	Age > 25 + bar-goers > 1/month → 62% vs. others → 55%
•	Bar-goers > 1/month + no kid passengers + non-agricultural job → 62%
•	Bar-goers > 1/month + under 30 → 63%
•	Frequent cheap restaurant-goers + income < 50K → 60%

## Part 3. Independent Investigation – Other Attributes
When destination is ‘No Urgent Place’, the acceptance rate is highest  0.63 vs ‘Work’ lowest 50%
When passanger is ‘Friend(s), the acceptance rate is highest  67% vs ‘Kid(s)’ lowest 50%
When weather is ‘Sunny’, the acceptance rate is highest  59% vs ‘Rainy’ lowest 46%
When temperature is ‘80’, the acceptance rate is highest  60% vs ‘30’  53%
When time is ‘2PM’, the acceptance rate is highest 66% vs ‘7AM’ lowest 50%
When expiration is ‘1d’, the acceptance rate is highest 62% vs ‘2h’ 50%
When age is ‘below21’, the acceptance rate is highest 63% and overall, the rate decreases with age increasing
Education shows the lower education level, the higher acceptance rate, the rate of ‘some high school’ is highest 72%
Occupation shows the rate for ‘retired’ is the lowest 46%, both ‘Healthcare Support’ and ‘Construction & Extraction’ are highest ~70%
Bar: Those who are more often to go to Bar, the higher acceptance rate, 4-8 times has the highest rate 64%
Restaurant20To50: Those who are more often to go to Restaurant20To50, the higher acceptance rate, more than 4 times has the highest rate 66%  

## Part 4. Correlation Analysis
Top 10 features most correlated with Y (coupon acceptance):
•	coupon_Carry out & Take away
•	coupon_Restaurant(<20)
•	destination_No Urgent Place
•	expiration_2h
•	passanger_Friend(s)
•	CoffeeHouse_never
•	toCoupon_GEQ25min
•	weather_Sunny
•	coupon_Coffee House
•	coupon_Restaurant(20-50)
These features showed moderate positive correlations with acceptance and support non-random, statistically significant influence which could be potential predictive variables.
Summary: Overall, these insights suggest that coupon acceptance is shaped by a combination of behavioral context (companions, time), situational factors (weather, destination urgency), and coupon type. The consistency between descriptive averages and inferential relationships strengthens confidence in these findings
Coupon type Carry out & Take away has the highest acceptance rate = 73% vs Bar lowest 41%
destination is ‘No Urgent Place’, the acceptance rate is highest  0.63 vs ‘Work’ lowest 50%
passanger is ‘Friend(s), the acceptance rate is highest  67% vs ‘Kid(s)’ lowest 50%
weather is ‘Sunny’, the acceptance rate is highest  59% vs ‘Rainy’ lowest 46%
temperature is ‘80’, the acceptance rate is highest  60% vs ‘30’  53%
time is ‘2PM’, the acceptance rate is highest 66% vs ‘7AM’ lowest 50%
expiration is ‘1d’, the acceptance rate is highest 62% vs ‘2h’ 50%
age is ‘below21’, the acceptance rate is highest 63% and overall, the rate decreases with age increasing
Education shows the lower education level, the higher acceptance rate, the rate of ‘some high school’ is highest 72%
Occupation shows the rate for ‘retired’ is the lowest 46%, both ‘Healthcare Support’ and ‘Construction & Extraction’ are highest ~70%
Bar: Those who are more often to go to Bar, the higher acceptance rate, 4-8 times has the highest rate 64%
Restaurant20To50: Those who are more often to go to Restaurant20To50, the higher acceptance rate, more than 4 times has the highest rate 66%  

 
## Part 5. Next Steps and Recommendations
1.	Data Expansion: Investigate outliers, duplicates, and potential sampling biases
2.	Feature Engineering: Create meaningful features, composite features, and/or interaction terms (e.g., age × time × coupon type)
3.	Multicollinearity Review: Use techniques like PCA or VIF to manage highly correlated features
4.	Feature Selection: Rank feature importance via statistical or model-based methods
5.	Modeling: Train models using logistic regression, decision trees, or ensemble methods
6.	Model Optimization: model tuning, testing, and validation to ensure generalizability
## Find a Bug?
If you found an issue or would like to submit an improvement to this project, please submit an issue using the issues tab above. If you would like to submit a PR with a fix, reference the issue you created. 
## Known Issues (Work in progress)
This project is still ongoing…
