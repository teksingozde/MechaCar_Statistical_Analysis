# MechaCar Statistical Analysis
## Overview of Project
The client has deemed it appropriate to perform some controls and analyzes for performance measurements of a new product, MechaCar.

Within this pressure analysis.
- MechaCar fuel efficiency (mpg) with linear regression
- t - tests on suspension coils
- All other required studies, One Way ANOVA, box plot, correlations.. 

### Resources
Data Sources: 
- MechaCar_mpg.csv
- Suspension_Coil.csv
Software: RStudio

## Overview of the Analysis 
#### Analysis 1. VIF Test
<img width="667" alt="VIF test" src="https://user-images.githubusercontent.com/26927158/210926045-6b8359df-212f-4be7-9dd3-b02a6479e3ba.png">
In order to obtain realistic values, linear regression needs to satisfy some assumptions. In multiple linear regression, multicollinearity problem may occur. We can continue the analysis by checking this. For this, the vif() function can be used in the car library in R.
As can be seen, the variance inflation factor (vif) value is very close to 1. When this value is close to 10 and above 10, it can be interpreted that there is a multicollinearity problem. It is seen that there is no such problem in our model.

#### Analysis 2. Multiple Linear Regression
<img width="571" alt="mechacar regression" src="https://user-images.githubusercontent.com/26927158/210926140-8a16adbb-b376-48e4-8857-c6b0c13a0029.png">
Linear regression is a data analysis technique that estimates the value of unknown data using another relevant and known data value. It mathematically models the unknown or dependent variable and the known or independent variable as a linear equation.
The easiest way to predict the fuel efficiency of MechaCar is with the linear regression model. The linear regression model is the most accurate method to explain the effect of each variable on fuel efficiency.

In this table, vehcle_length and argument_clearance argument are the variables that best describe the dependent variable of the model. It is seen that the p value in vehicle_length and ground_clearance variables is below 0.05, that is, the H0 hypothesis is rejected and we can say that these variables are significant. Other independent variables, namely vehicle_weight, spoiler_angle and AWD variables, were found to be meaningless. When interpreting the regression model, the Adjusted R-Squared value gives the explanatory percentage of the model. Commenting on this regression model, 68.25% of the total change in fuel efficiency is explained by vehicle_length, vehicle_weight, spoiler_angle, ground_clearance, and AWD. This model shows that the model with the adjusted R-squared value is an intermediate model. For better fuel efficiency, vehicle_weight, spoiler_angle and AWD values should be removed from the model. In this case, the adjusted R-squared value will increase. However, since the vehicle_weight argument is very close to 0.05, it does not have a positive or negative effect on the model. Therefore, it can be added to the model.

#### Analysis 3. Distribution of Residuals
![Residuals Distribution](https://user-images.githubusercontent.com/26927158/210926727-4f26c707-9ba8-41e8-94f9-30c273c011da.png)
Another hypothetical check is the regular Q-Q chart. These above tables show us whether the residues are normally distributed or not. Looking at the normal Q-Q graph; It shows us that residuals 4, 27 and 33 can be removed from the data set.

#### Analysis 4. Shapiro Wilk Test
<img width="591" alt="Shapiro Wilk test" src="https://user-images.githubusercontent.com/26927158/210926467-5d2988dd-2150-49c2-91f8-42d958ebefe5.png">
Since p=0.7965 > 0.05 in the Shapiro Wilk test, it can be interpreted that the residues are normally distributed.

#### Analysis 5. Correlations
<img width="572" alt="correlations" src="https://user-images.githubusercontent.com/26927158/210926627-f9e77a47-b0d0-409d-b0da-38cbafe7def5.png">
Correlation coefficient (r), the relationship between two variables
is the size. Change of correlation coefficient between -1 and +1
shows.
r= ( + ); there is a perfect positive linear relationship,
r= ( - ); there is a perfect negative linear relationship
It means.

Regarding the strength of the coefficient of correlation
The following definitions have been made:
0.00 - 0.25 Very weak relationship
0.26 - 0.49 Poor relationship
0.50 - 0.69 Medium relation
0.70 - 0.89 High correlation
0.90 - 1.00 Very high correlation

Considering the correlation coefficients;
- Positive moderate correlation relationship between mpg dependent variable and vehicle_length independent variable,
- Positive and very weak correlation between mpg dependent variable and vehicle_weight independent variable,
- Very weak correlation relationship in the negative direction between the mpg dependent variable and the spoiler_angle independent variable,
- Positive and weak correlation relationship between mpg dependent variable and ground_clearance independent variable,
- There is a very weak correlation in the negative direction between the mpg dependent variable and the AWD independent variable.

<img width="613" alt="Screen Shot 2023-01-05 at 4 04 46 PM" src="https://user-images.githubusercontent.com/26927158/210926757-ce3c6ab5-e4a2-4b0b-8887-129b3410cd37.png">
As can be seen from the correlation graphs above, there is a very minimal relationship between the factors examined in terms of affecting each fuel efficiency and fuel efficiency. The variables that need to be examined and researched in terms of fuel efficiency should be vehicle_length and ground_clearance.

<img width="324" alt="image" src="https://user-images.githubusercontent.com/26927158/210928583-bea998df-667e-45a5-8d5a-641ed8466192.png">
The box plot for the AWD variable compares the line in the middle of the boxes, that is, the medians. If the median line of one boxplot is outside the box of another boxplot, a difference is likely between the two groups.
For the AWD variable, when the scatter plot is also analyzed instead of the box plot, it is clearly seen that there is no negative line or even relationship between the variables.
If a general comment is to be made, different types of assumption tests should be made before and during the multiple regression model. First of all, it should be properly examined whether the independent variables of the model are significant variables, and if there are outliers in our data set, they should be removed. In other words, non-significant variables should be removed from the independent variables and the data should be cleaned so that a new model can be established and analyzed with the significant variables in our model.

### Analysis of Suspension Coil
#### Analysis 6. Total Summary PSI
<img width="363" alt="image" src="https://user-images.githubusercontent.com/26927158/210928611-27dd32f2-8400-4dcc-b07a-cd2ce01b0649.png">
PSI is the name given to the air pressure values in tires. In general, the average of the PSI values in our data set is 1498.78, the median value is 1500, the variance value shows how different our observation values can be from the average, and the variance value is 62.29. The standard deviation value is 7.89, and the smaller the standard deviation value, the closer the data are to the mean. In this dataset, the data are very close to the mean. The fact that the arithmetic mean is smaller than the median indicates that the frequency curve is left skewness, even at the minimum level, but this skewness is close to the symmetrical distribution, because there is not much difference between the median and the mean.

#### Analysis 7. Lot1 - Lot2- Lot3 Summary
<img width="492" alt="image" src="https://user-images.githubusercontent.com/26927158/210928639-3e33e44d-d7e5-446a-a9c7-0fe9ad2cf359.png">
In the data set, the concept of lot takes place in the form of grouping. While the mean and median of the data belonging to the Lot1 group are equal to each other, at the same time, the variance and standard deviation values are very low. This means that all data belonging to lot1 group are symmetrical.
In the data belonging to the lot2 group, the mean and the median are equal, indicating that the data belonging to the lot2 group are symmetrical. The standard deviation value is very small. It shows that the data are close to the mean.
The data belonging to the Lot3 group is the group of data that causes the frequencies in the general statistical summary table of the PSI values to be skewed to the left. In this group, the data are generally far from the mean and the frequency distribution is skewness to the left. The high variance value also clearly shows that our PSI observation values are very different from the mean.

#### Analysis 8. Lots Histogram Plots (PSI Observation Values)
<img width="486" alt="image" src="https://user-images.githubusercontent.com/26927158/210928677-4e9ca353-ae22-4d07-9a80-fc33588625d8.png">
Considering the distributions of lot1, lot2 and lot3 observation values, while lot1 and lot2 observation values are clearly symmetrical for lot1, there is no skewness in lot2. However, lot3 is completely left skewness.

#### Analysis 9. PSI t-test
<img width="478" alt="image" src="https://user-images.githubusercontent.com/26927158/210928719-425db3ad-a085-4954-9ebb-6ed3b57fbf03.png">
Parametric tests assume that the data has a normal distribution.

The overall mean of the PSIs should be 1497<mean(PSI)<1500.053. The mean of x is 1498.78, so it falls between the confidence interval.

H0: Average is equal to 1500.
H1: Average is not equal to 1500.

If p = 0.06028 > 0.05, statistically H0 is accepted at 95% confidence interval. So the average is not equal to 1500.

#### Analysis 10. Lot1 t-test
<img width="478" alt="image" src="https://user-images.githubusercontent.com/26927158/210927379-e1ef391e-6448-47ca-ba1e-6de7f1b79575.png">
The overall mean of Lot1 should be 1499.719<mean(lot1)<1500.281. The mean of x is 1500, so it falls between the confidence interval.

H0: Average is equal to 1500.
H1: Average is not equal to 1500.

If p = 1 > 0.05, statistically H0 is accepted at 95% confidence interval. So the average is equal to 1500.

#### Analysis 11. Lot2 t-test
<img width="478" alt="image" src="https://user-images.githubusercontent.com/26927158/210927432-b1d9f89c-0ce7-4998-8ac4-3afdef2c6c18.png">
The overall mean of lot2 should be 1499.423<mean(lot2)<1500.977. The mean of x is 1500.2, so it falls between the confidence interval.

H0: Average is equal to 1500.
H1: Average is not equal to 1500.

If p = 0.6072 > 0.05, statistically H0 is accepted at 95% confidence interval. So the average is equal to 1500. 

#### Analysis 11. Lot3 t-test
<img width="478" alt="image" src="https://user-images.githubusercontent.com/26927158/210927549-5cb7eaba-1866-48ce-bb92-80e3519fc522.png">
The overall mean of lot3 should be 1492.431<mean(lot3)<1499.849. The mean of x is 1498.78, so it falls between the confidence interval.

H0: Average is equal to 1500.
H1: Average is not equal to 1500.

If p = 0.04168 > 0.05, statistically H1 is accepted at 95% confidence interval. So the average is not equal to 1500.

#### Analysis 12. Lot1-Lot2 Paired t-test
<img width="478" alt="image" src="https://user-images.githubusercontent.com/26927158/210927607-e03ddf2f-2443-4815-b26b-487363ab0505.png">

#### Analysis 12. Lot1-Lot2 Paired t-test
Paired t-test is a technique used to test the significance of the difference between the arithmetic means of two related groups, provided that n>30 or the normality of the distribution.

<img width="478" alt="image" src="https://user-images.githubusercontent.com/26927158/210927761-87e79738-4fae-4b77-a6aa-fa91ab274e1b.png">
H0: There is no statistically significant difference between the means of lot1 and lot2.
H1: There is a statistically significant difference between the means of lot1 and lot2.

Since p = 0.6052 > 0.05, Ho is accepted. That is, there is no statistically significant difference between the averages of lot1 and lot2 at the 95% confidence interval. The confidence interval value is -0.9724591 < mean difference< 0.05724591. Mean difference = -0.2 and stays in confidence interval.

#### Analysis 13. Lot1-Lot3 Paired t-test
<img width="478" alt="image" src="https://user-images.githubusercontent.com/26927158/210927829-fbbf04a2-cdc3-47a8-8ddb-7f7037d4443c.png">
H0: There is no statistically significant difference between the means of lot1 and lot3.
H1: There is a statistically significant difference between the means of lot1 and lot3.

Since p = 0.04347 < 0.05, H1 is accepted. That is, there is a statistically significant difference between the averages of lot1 and lot3 at the 95% confidence interval. The confidence interval value is 0.1177828 < mean difference < 7.6022172. Mean difference = 3.86 and it falls between confidence interval.

#### Analysis 14. Lot2-Lot3 Paired t-test
<img width="478" alt="image" src="https://user-images.githubusercontent.com/26927158/210927926-e992b287-9442-4240-a341-48f64dc80133.png">
H0: There is no statistically significant difference between the means of lot2 and lot3.
H1: There is a statistically significant difference between the means of lot2 and lot3.

Since p = 0.04199 < 0.05, H1 is accepted. That is, there is a statistically significant difference between the averages of lot2 and lot3 at the 95% confidence interval. The confidence interval value is 0.1529772 < mean difference< 7.9670228. Mean difference = 4.06 and it falls between confidence interval.

#### Analysis 15. One Way ANOVA Test
<img width="478" alt="image" src="https://user-images.githubusercontent.com/26927158/210927972-94917f71-b847-43af-86c3-18be07a9f642.png">
This test is applied if there are at least three independent samples or groups.
H0: µlot1 = µlot2 = µlot3
H1: At least one μ value is different.

Since the F statistical value is 17.94 and the significance level of the corresponding p value is p = 0.014 < 0.05, the average PSI values of each lot are not equal to each other. So at least one is different. Tukey test is applied to find out which one is different.

#### Analysis 16. Tukey Test
<img width="478" alt="image" src="https://user-images.githubusercontent.com/26927158/210928025-ee0755e8-7a15-442b-b34a-6437a6816e0e.png">
Confidence value for Tukey HSD is 0.05. As a result of the above analysis, the "diff" column provides average differences. The "lwr" and "upr" columns provide lower and upper 95% security limits, respectively. Finally, the “p adj” column provides the adjusted p-values for the number of comparisons made. It turns out that this difference is due to lot3.

The results show that there is a statistically significant difference compared to the Tukey Test except lot2-lot1. 

<img width="478" alt="image" src="https://user-images.githubusercontent.com/26927158/210928087-24602ece-45bf-4617-82fc-7f9b90e4034a.png">
The Tukey test plot gives us information about the lot that made the difference. As can be seen, the difference is largely due to the lot3 group.














