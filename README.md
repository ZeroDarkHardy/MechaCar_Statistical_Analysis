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

Our [Suspension Coil dataset](https://github.com/ZeroDarkHardy/MechaCar_Statistical_Analysis/blob/main/Resources/Suspension_Coil.csv) contains the results from muple production lots. We created statistical summary dataframes to ascertain whether the manufacturing process is consistent between the various facilities

![deliverable2_code.png](https://github.com/ZeroDarkHardy/MechaCar_Statistical_Analysis/blob/main/images/deliverable2_code.png)

-Using the code shown above, we created our statistical summaries.

![total_summary_df.png](https://github.com/ZeroDarkHardy/MechaCar_Statistical_Analysis/blob/main/images/total_summary_df.png)


![lot_summary_df.png](https://github.com/ZeroDarkHardy/MechaCar_Statistical_Analysis/blob/main/images/lot_summary_df.png)


## T-Tests on Suspension Coils

![deliverable3_1.png](https://github.com/ZeroDarkHardy/MechaCar_Statistical_Analysis/blob/main/images/deliverable3_1.png)

![deliverable3_2.png](https://github.com/ZeroDarkHardy/MechaCar_Statistical_Analysis/blob/main/images/deliverable3_2.png)

![deliverable3_3.png](https://github.com/ZeroDarkHardy/MechaCar_Statistical_Analysis/blob/main/images/deliverable3_3.png)

![deliverable3_4.png](https://github.com/ZeroDarkHardy/MechaCar_Statistical_Analysis/blob/main/images/deliverable3_4.png)

## Comparison Study: MechaCar vs. Competition