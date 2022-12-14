# MechaCar_Statistical_Analysis
Summary Statistics on Suspension Coils

In the lot summary, the major contributor to the variance is lot 3 with a variance of 170 PSI with the other lots having variances at or below 8 PSI.

In the total summary, the variance of all three lots in total is under the maximum variance of 100 PSI with a variance of 62 PSI.

The data meets the maximum variance in PSI requirement, but there are issues in lot 3 with a variance of 170 PSI. Lot 3 does not meet the maximum variance requirement.

![Lot summary](https://user-images.githubusercontent.com/108476566/201797516-b31017f6-bf0e-4585-acbd-aca28e970fac.png)
![total summary](https://user-images.githubusercontent.com/108476566/201797908-b2a4b38d-22ad-4cee-b45b-f7d6752b5738.png)

T-Tests on Suspension Coils

Performing the first t-test, the sample mean is not different from the population mean of 1500 PSI with a p-value of 0.06.

When I perform t-tests on the individual lots, lots 1 and 2 are not statistically different from the population mean with p-values of 1 and 0.6 respectively, lot 3 does have a mean that is statistically different from the population mean with a p-value of 0.04.


> #1. use t.test() to determine if the PSI across ALL lots is statistically different from the pop. mean of 1,500 PSI.
> t.test(mecha_coil$PSI,mu=1500)

	One Sample t-test

data:  mecha_coil$PSI
t = -1.8931, df = 149, p-value = 0.06028
alternative hypothesis: true mean is not equal to 1500
95 percent confidence interval:
 1497.507 1500.053
sample estimates:
mean of x 
  1498.78 

> #2. Use t.test() function 3 more times with subset() to determine if PSI for each manufacturing lot is statistically different from the pop. mean of 1,500 PSI
> lot1 <- subset(mecha_coil, Manufacturing_Lot=="Lot1")
> lot2 <- subset(mecha_coil, Manufacturing_Lot=="Lot2")
> lot3 <- subset(mecha_coil, Manufacturing_Lot=="Lot3")
> 
> t.test(lot1$PSI,mu=1500)

	One Sample t-test

data:  lot1$PSI
t = 0, df = 49, p-value = 1
alternative hypothesis: true mean is not equal to 1500
95 percent confidence interval:
 1499.719 1500.281
sample estimates:
mean of x 
     1500 

> t.test(lot2$PSI,mu=1500)

	One Sample t-test

data:  lot2$PSI
t = 0.51745, df = 49, p-value = 0.6072
alternative hypothesis: true mean is not equal to 1500
95 percent confidence interval:
 1499.423 1500.977
sample estimates:
mean of x 
   1500.2 

> t.test(lot3$PSI,mu=1500)

	One Sample t-test

data:  lot3$PSI
t = -2.0916, df = 49, p-value = 0.04168
alternative hypothesis: true mean is not equal to 1500
95 percent confidence interval:
 1492.431 1499.849
sample estimates:
mean of x 
  1496.14 

Study Design: MechaCar vs Competition

When comparing the performance of the MechaCar versus the competition, I reviewed a few variables of interest to potential customers. These variables are cost, city, horsepower, highway fuel efficiency, safety rating, and carbon waste output.

I will be testing if MechaCar has statistically significant differences in these metrics compared to the competition. 

The null hypothesis: variables are not significantly different from the competition.  
Alternative hypothesis: MechaCar is significantly different in these variables compared to the competition.

I would perform one-tailed t-tests in order to determine if the MechaCar has higher or lower observed values in these variables. The potential customer would prefer cost to be lower, the city and highway fuel efficiency to be higher, the horsepower to be higher, the safety rating to be higher, and the carbon waste output to be lower.

In order to run these tests, this information is required: the cost, fuel efficiency, horsepower, safety rating, and carbon waste output data from the MechaCar. In addition, the MechaCar's competitors.
