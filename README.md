# MechaCar_Statistical_Analysis,
 
## BACKGROUND: 
AutosRU’s a vehicle manufacturing company, recently hired DYPCreator Data Analytics Team to help them solve a pressing problem. 
#### PROBLEM: 
The production of AutoRU’s newest car model, “MechaCar,” is suffering, and the Auto’sRU executive wants to understand the factors that are impacting production so that they can quickly fix the problem. 

#### RESOURCES: 
AutoRU has provided DYPCreators with data set from AutoRU’s new prototype MechCar, which we will utilize In this MechaCar_Statistical_Analysis. In addition, this project will leverage the power of R & R Studio’s Built-in Functions & Libraries packages.

## Deliverable 1: Linear Regression to Predict MPG
The first dataset, MechaCar_mpg.csv, contains AutoUR mile per hour testing on 50 MechaCar prototypes. The AutopRU manufacturing team's test results consist of the following metric, which will serve as the variables(columns) in our analysis. : vehicle length, vehicle weight, spoiler angle, drivetrain, and ground clearance. Before analyzing the data, we first establish the following: 

#### ALPHA VALUE: 
We will use the standard value of 0.05 or 50%

#### TEST TYPES: 
The first analysis consists of linear modules. Linear models are used in statistics to help predict the value of a variable based on the value of another variable. 

#### QUESTION: 
How much variance in the dependent variable mpg is accounted for in a linear combination of the independent variables vehicle length, vehicle weight, spoiler angle, drivetrain, & ground clearance? In other words, can we predict the mpg of MechaCar prototypes using the values of the vehicle length, vehicle weight, spoiler angle, drivetrain, & ground clearance metrics variables? Does a relationship exist?

#### NULL HYPNOSIS: 
H0: We CANNOT predict the mpg based on the given variable
Linear Model: H0: The slope of the linear model is zero, or m = 0)

#### HYPOTHESIS: 
Ha: We CAN predict the mpg based on the given variable
Linear Model: Ha: The slope of the linear model is not zero, or m ≠ 0

# Logical Workflow 
1.	We begin by loading our data and converting it into a data frame setting the data frame to the variable mpg_data_table. 
2. We then leverage R’s lm() function to perform multiple linear regression calculations. The linear regression is used to calculate the slope and the coefficients. The lm () function takes several arguments; the two arguments we will use for this project are formula and data. lm(formula, data,) or m(y ~ x1 + x2 + x3 + x4 +x5, data=name_of_DF)

#### Formula Argument:  

The y value is the Dependent Variable aka OutCome Variable (mpg) 
The X values are the Five independent variables, aka Predictor Variable. 

#### Data Argument: 

mpg_data_table.

3. We use R’s summary() function to get our statistical metrics summary, including p-value and R-value for our multiple linear regression model. The R-value will help us in determining if the model adequately predicts our mpg variable.

Variable | Coefficients:| Second Header
------------ | ------------- | -------------
(Intercept) | -1.040e+02  | 5.08e-08 ***
vehicle_length |  6.267e+00  | 2.60e-12 ***
vehicle_weight |  1.245e-03   | 0.0776
spoiler_angle  |  6.877e-02  | 0.3069 
ground_clearance  | 3.546e+00   | 5.21e-08 ***
 AWD | -3.411e+00  | 0.1852  
 
 
 Multiple R-squared |  P-value
------------ | -------------
0.7149| 5.35e-11
72%| 5.35 × 1011

## Deliverable 1 Summary

In the summary output of the mpg_data_table, each Pr(>|t|) value represents the probability that each coefficient contributes a random amount of variance to the linear model. 

According to our results, vehicle_length and ground_clearance and the intercept significantly impact miles per gallon(mpg). Therefore we can conclude that they are statistically unlikely to provide random variances to our linear model. 

The R-square value from our linear model is 0.7149 or 72% 
The P-Value from our linear model is 5.35e+11 or 5.35 × 1011 or 535000000000.0

# Deliverable 2: Summary Statistics on Suspension Coils
The second dataset, MechaCar_mpg.csv, contains AutoUR mile per hour testing on 50 MechaCar prototypes. The AutopRU manufacturing team's test results consist of the following metric, which will serve as the variables(columns) in our analysis. : vehicle length, vehicle weight, spoiler angle, drivetrain, and ground clearance. Before analyzing the data, we first establish the following:
 MEAN  | MEDIAN | SD | VARIANCE
------------ | ------------- | -------------| -------------
1498.78| 1500	 |  7.892627	| 	62.29356
Content column 1 | Content column 2 | Content column 2 | Content column 2



Manufacturing_Lot | MEAN | MEDIAN  | SD | VARIANCE
------------ | ------------- | -------------| ------------- | -------------
Lot 1 | 1500 | 1500.0	 | 0.9897433| 0.9795918
Lot 2 | 1500.20 | 1500.0  | 2.7330181 | 7.4693878
Lot 3 | 1496.14 | 1498.5| 13.0493725	 | 170.2861224
 
 
 

                                     


                        
  

