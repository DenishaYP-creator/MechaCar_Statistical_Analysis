# MechaCar_Statistical_Analysis,
 
## BACKGROUND: 
AutosRU’s a vehicle manufacturing company, recently hired DYPCreator Data Analytics Team to help them solve a pressing problem. 
##### PROBLEM: 
The production of AutoRU’s newest car model, “MechaCar,” is suffering, and the Auto’sRU executive wants to understand the factors that are impacting production so that they can quickly fix the problem. AutoRU has provided DYPCreators with data sets from AutoRU’s new prototype MechCar and their manufacturing lot, which we will utilize in this MechaCar_Statistical_Analysis. 

**In this project will leverage the power of R/R Studio’s Built-in Functions & Libraries packages to perfrom the required calculations and plot the the results.**

## Project Deliverables 
The  MechaCar_Statistical_Analysis consist of 4 deliverables as follows:

Deliverable|Title 
------------ | -------------
Deliverable 1| Linear Regression to Predict MPG
Deliverable 2 | Summary Statistics on Suspension Coils
Deliverable 3 | T-Test on Suspension Coils
Deliverable 4 | Design a Study Comparing the MechaCar to the Competition

<hr> </hr> 

## Deliverable 1: Linear Regression to Predict MPG

The first dataset, MechaCar_mpg.csv, contains AutoUR mile per hour testing on 50 MechaCar prototypes. The AutopRU manufacturing team's test results consist of the following metric, which will serve as the variables(columns) in our analysis. : vehicle length, vehicle weight, spoiler angle, drivetrain, and ground clearance. Before analyzing the data, we first establish the following: 

##### ALPHA VALUE: 
We will use the standard value of 0.05 or 50%

#####  TEST TYPES: 
The first analysis consists of linear modules. Linear models are used in statistics to help predict the value of a variable based on the value of another variable. 

#####  QUESTION: 
How much variance in the dependent variable mpg is accounted for in a linear combination of the independent variables vehicle length, vehicle weight, spoiler angle, drivetrain, & ground clearance? In other words, can we predict the mpg of MechaCar prototypes using the values of the vehicle length, vehicle weight, spoiler angle, drivetrain, & ground clearance metrics variables? Does a relationship exist?

NULL HYPNOSIS | HYPOTHESIS
------------ | -------------
H0: We CANNOT predict the mpg based on the given variable | Ha: We CAN predict the mpg based on the given variable
H0: The slope of the linear model is zero, or m = 0) | Ha: The slope of the linear model is not zero, or m ≠ 0


# Logical Workflow 
1.	We begin by loading our data and converting it into a data frame setting the data frame to the variable mpg_data_table. 
2. We then leverage R’s lm() function to perform multiple linear regression calculations. The linear regression is used to calculate the slope and the coefficients. The **lm () function"" takes several arguments; the two arguments we will use for this project are formula and data. **lm(formula, data) The Data Argument is equal to the data table: mpg_data_table.

Formula Argument | lm(formula, data) or lm(y ~ x1 + x2 + x3 + x4 + x5)
------------ | -------------
y value  | The y value is the Dependent Variable aka OutCome Variable (mpg) 
x value  | The x values are the Five independent variables, aka Predictor Variable.

3. We use R’s **summary() function** to get our statistical metrics summary, including p-value and R-value for our multiple linear regression model. The R-value will help us in determining if the model adequately predicts our mpg variable.

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

##### Question 1: Which variables/coefficients provided a non-random amount of variance to the mpg values in the dataset?

In the summary output of the mpg_data_table, each Pr(>|t|) value represents the probability that each coefficient contributes a random amount of variance to the linear model. 

According to our results, vehicle_length, ground_clearance and the intercept significantly impact miles per gallon(mpg). Therefore we can conclude that they are statistically unlikely to provide random variances to our linear model. 

##### Question 2: Is the slope of the linear model considered to be zero? Why or why not?
The P-Value from our linear model is 5.35e+11 or 5.35 × 1011 or 535000000000.0 is smaller than our alpha value of 0.05.
As a result, we can state that there is sufficient evidence to reject our null hypothesis, which means that the slope of our linear model is not zero.


##### Question 3: Does this linear model predict mpg of MechaCar prototypes effectively? Why or why not?
The R-square value from our linear model is 0.7149 or 72%, which means that roughly 72% of the variablilty of our  miles per gallon- mpg (dependent variable) is explained using this linear model.

[![MPG-Plots.png](https://i.postimg.cc/FR7drPHB/MPG-Plots.png)](https://postimg.cc/JDC4K5JN)

<hr> </hr> 



# Deliverable 2: Summary Statistics on Suspension Coils
##### Summary Statistics on Suspension Coils
The second dataset, 'Suspension_Coil.csv', contains AutoUR PSI for three manufacturing lots.The AutopRU manufacturing team's test results consist of the following metric, which will serve as the variables(columns) in our analysis. :VehicleID, Manufacturing_Lot, and PSI  . Before analyzing the data, we first establish the following:

##### QUESTION:
Is the manufacturing process consistent across production lots?

NULL HYPNOSIS | HYPOTHESIS
------------ | -------------
H0: Manufacturing process **IS NOT** consistent across production lots| Ha: Manufacturing process **IS** consistent across production lots

##### ALL PRODUCTION LOTS SUMMARY RESULTS:

 MEAN  | MEDIAN | SD | VARIANCE
------------ | ------------- | -------------| -------------
1498.78| 1500	 |  7.892627	| 	62.29356


##### INDIVDUAL LOTS PRODUCTION LOTS SUMMARY RESULTS:

Manufacturing_Lot | MEAN | MEDIAN  | SD | VARIANCE
------------ | ------------- | -------------| ------------- | -------------
Lot 1 | 1500 | 1500.0	 | 0.9897433| 0.9795918
Lot 2 | 1500.20 | 1500.0  | 2.7330181 | 7.4693878
Lot 3 | 1496.14 | 1498.5| 13.0493725	 | 170.2861224

 
## Deliverable 2 Summary: 
The design specifications for the MechaCar suspension coils dictate that the variance of the suspension coils cannot be greater than 100lbs per square inch. 
- The current manufacturing data confirms the variance of the suspension coil for all manufacturing lots in total is 62 pounds therefore it meets the design specification. 
- The current manufacturing data confirms the variance of the suspension coil for manufacturing **lot 1** is ** 98 pounds**, **lot 2** is ** 7 pounds**, and **lot 3** is ** 170 pounds**,  therefore we can state that manufacturing lot & and 2 meet the design specification.




<hr> </hr> 
 
# Deliverable 3: T-Tests on Suspension Coils 

##### ALPHA VALUE: 
We will use the standard value of 0.05 or 50%

#####  TEST TYPES: T-Test 
T-test are use to compare two data set from another. 

#### QUESTION1:
Are all manufacturing lots statistically different from the population mean of 1,500 pounds per square inch? 
#### QUESTION2:
Is the manufacturing of individual lots statistically different from the population mean of 1,500 pounds per square inch?

NULL HYPNOSIS | HYPOTHESIS
------------ | -------------
H0: There is NO stastiscally difference | Ha: There IS a stastiscally difference

#### Answer 1: 
The P-values of of the All manufacturing lots data set is 0.06028 or 6% which is above our Alpha value of  0.05 or 5%, as a reult, we can conclude that we have sufficient evidence to reject the null hypothesis. Furthermore, we would state that a statistical difference exists between the between population mean of 1500 pounds per square inch and the mean of all manufacturing data.

#### Answer 2: 
Our Alpha Value| 0.05 or 5%

Lot | P-Value | Results 
------------ | -------------| -------------
Lot 1 | 0.06072 or 6% | There IS A stastiscally difference 
Lot 2 | 1.00 |  There is NO stastiscally difference 
Lot 3 | 0.04168 |  There is NO stastiscally difference 


#### RESULTS 
[![Lots-Data-Plots.png](https://i.postimg.cc/wMw7vgMK/Lots-Data-Plots.png)](https://postimg.cc/rRt8Z65g)


# Deliverable 4: Design a Study Comparing the MechaCar to the Competition
#####  Study Design: MechaCar vs Competition.
In the last deliverable we will conduct a statistical study comparing MechaCar vehicles performance (mpg) against vehicles performance (mpg) from other manufacturers. We will use the MechaCar dataset and the R mtcars data set.

##### The metric we will measure is MPG or Mile per Gallon

##### Question:
Is there a statically difference between the mpg performance of Mecha Car vehicles & the mpg performance of other vehicles 

#####  TEST TYPES: Two Paired T-Test 
T-test are use to compare two sample from two different populuations.

##### ALPHA VALUE: 
We will use the standard value of 0.05 or 50%

NULL HYPNOSIS | HYPOTHESIS
------------ | -------------
H0 : The difference between our paired observations (the true mean difference, or "μd") is equal to zero. |Ha : The difference between our paired observations (the true mean difference, or "μd") is not equal to zero.

                               
[![Stat-Test.png](https://i.postimg.cc/52ZZ1sYm/Stat-Test.png)](https://postimg.cc/nXGdGY1s)




