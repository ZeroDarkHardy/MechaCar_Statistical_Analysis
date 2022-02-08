# MechaCar_Statistical_Analysis

Performing statistical analysis of vehicle performance using R

## Overview of Project

AutosRUs' newest prototype, the MechaCar, is experiencing troubles that are inhibiting the manufaturing process. The company has requested that our analytics team review the production data for insights that may help resolve the issue.

## Resources

Software/Languages: R v4.1.2, RStudio build 382 "Ghost Orchid"

Source Data: [MechaCar MPG dataset](https://github.com/ZeroDarkHardy/MechaCar_Statistical_Analysis/blob/main/Resources/MechaCar_mpg.csv), [Suspension Coil dataset](https://github.com/ZeroDarkHardy/MechaCar_Statistical_Analysis/blob/main/Resources/Suspension_Coil.csv)

Finished R Script: [MechaCarChallenge.R](https://github.com/ZeroDarkHardy/MechaCar_Statistical_Analysis/blob/main/MechaCarChallenge.R)

---

## Linear Regression to Predict MPG

Given a [dataset](https://github.com/ZeroDarkHardy/MechaCar_Statistical_Analysis/blob/main/Resources/MechaCar_mpg.csv) containing MPG test results for 50 prototype MechaCars, we designed a linear model to predict MPG using several variables.

![linear_regression.png](https://github.com/ZeroDarkHardy/MechaCar_Statistical_Analysis/blob/main/images/linear_regression.png)

- When we examine our linear model, two coefficients show a non-random amount of variance:
    - Vehicle length, which has a P-value of 2.6x10<sup>-12</sup>.
    - Ground clearance, with a P-value of 5.21x10<sup>-8</sup>.
- It is also worth noting that the Intercept shows a staticly significant P-value as well, which suggests that there may be other factors (outside of our dataset) that have an impact on MPG results.
- The slope of the linear model can not be considered to be zero.  At the lower right of the screenshot shown above, we observe that the P-value of our multiple linear regression is 5.35x10<sup>-11</sup>, which is **EXTREMELY** significant, and certainly enough to reject our null hypothesis. 
- The R-squared (coefficient of multiple determination) for the model is 0.7149, signifying that our model explains 71% of the variance in the dataset. While this is a high enough value to assert confidence in our model's predictions, a larger dataset may increase this metric.

## Summary Statistics of Suspension Coil Data

Our [Suspension Coil dataset](https://github.com/ZeroDarkHardy/MechaCar_Statistical_Analysis/blob/main/Resources/Suspension_Coil.csv) contains the results from multiple production lots. We created statistical summary dataframes to ascertain whether the manufacturing process is consistent between the various facilities.

![deliverable2_code.png](https://github.com/ZeroDarkHardy/MechaCar_Statistical_Analysis/blob/main/images/deliverable2_code.png)

-Using the code shown above, we created our statistical summaries.

Summary Statistics for total population of dataset:<br/>
![total_summary_df.png](https://github.com/ZeroDarkHardy/MechaCar_Statistical_Analysis/blob/main/images/total_summary_df.png)

Summary Statistics for each production lot:<br/>
![lot_summary_df.png](https://github.com/ZeroDarkHardy/MechaCar_Statistical_Analysis/blob/main/images/lot_summary_df.png)

- The range of variance shown in our Total Summary dataframe is within acceptable limits, but when we examine the metrics from the three different lots, we see that the vast majority of that variance is coming from a single lot: Lot 3.
-  Lot 3 shows a variance range of 170.286, well outside of our acceptable limits.  The standard deviation shown in that lot's data is also almost 480% larger than the next lower value among the lots.  This implies that there are irregularities in the manufacturing process at Lot 3 (perhaps inconsistencies in workplace procedures, equipment or materials).
- Lot 1 shows the most consistency in their data values, by far.  If the company is satisfied by the work quality of Lot 1, it should be used as a training and logistics model for all lots.


## T-Tests on Suspension Coils

We performed T-Tests on the Suspension Coil dataset to determine if all manufacturing lots, and each lot individually, are statistially different from the population mean of 1,500 pounds per square inch (PSI).

T-Test of whole population:<br/>
![deliverable3_1.png](https://github.com/ZeroDarkHardy/MechaCar_Statistical_Analysis/blob/main/images/deliverable3_1.png)<br/>
- The T-Test for all manufacturing lots shows that they are not statistically different from the population mean.  The P-value of 0.06028 is *almost* but not quite low enough to reject the null hypothesis.

Manufacturing Lot 1:<br/>
![deliverable3_2.png](https://github.com/ZeroDarkHardy/MechaCar_Statistical_Analysis/blob/main/images/deliverable3_2.png)<br/>
- This T-Test shows a P-Value of 1, which is not low enough to reject the null hypothesis.  This lot's data shows no statistically significant difference from the population mean of 1500.

Manufacturing Lot 2:<br/>
![deliverable3_3.png](https://github.com/ZeroDarkHardy/MechaCar_Statistical_Analysis/blob/main/images/deliverable3_3.png)<br/>
- This T-Test shows a P-Value of 0.6072, which is not low enough to reject the null hypothesis.  This lot's data shows no statistically significant difference from the population mean of 1500.

Manufacturing Lot 3:<br/>
![deliverable3_4.png](https://github.com/ZeroDarkHardy/MechaCar_Statistical_Analysis/blob/main/images/deliverable3_4.png)<br/>
- The P-value of this T-Test shows a slight statistical difference from the population mean. At 0.04168, this P-value is low enough for us to reject the null hypothesis.  Either this data needs to be collected again after addressing the irregularities in production quality at this lot, or this lot's data needs to be discarded to more accurately guage the work product of the other two lots.

## Comparison Study: MechaCar vs. Competition

Our [MechaCar MPG dataset](https://github.com/ZeroDarkHardy/MechaCar_Statistical_Analysis/blob/main/Resources/MechaCar_mpg.csv) provides a general MPG rating for each vehicle produced, but another useful statistical comparison to make against the company's competitors would be to collect separate data for both highway and city-street fuel efficiency.  This is an important metric that many of today's commuters consider when purchasing a new car.

- This comparison would likely need to be compartmentalized into smaller categories, allowing us to compare fuel efficiency between these driving environments for vehicles with similar drive types (AWD vs. 2WD).  The metrics to consider when performing this statistical comparison are:
    - City and Highway fuel effiency as dependent variables
    - Drivetrain type (2WD, 4WD, AWD) as independent variables (our dataset only contains a boolean value for the presence of AWD, more data will need to be collected to supplement our current dataset)
    - Horsepower as an independent variable (not included in our current dataset, which will need to be supplemented)
- Since we noticed a few important coeffients earlier, it would be good to see if those variables produce similar correlations in competitor data (this can be accomplished by performing the same tests on competitor data that we have here, and comparing the results):
    - Vehicle length as an independent variable
    - Ground clearance as an independent variable
- Our null hypothesis would state that there is no statistical difference between the MechaCar and its competitors, when compared against similar categorical types.  
    