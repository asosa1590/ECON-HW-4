# ECON-HW-4

Lab 4
```
> load("/cloud/project/acs2017_ny_data.RData")
> attach(acs2017_ny)

> model_temp1 <- lm(INCWAGE ~ AGE + female + AfAm + Asian + Amindian + race_oth + Hispanic + educ_hs + educ_somecoll + educ_college + educ_advdeg)

> model_temp1 <- lm(INCWAGE ~ AGE + female + AfAm + Asian + Amindian + race_oth + Hispanic + educ_hs + educ_somecoll + educ_college + educ_advdeg)
> delete(odel_temp1)
Error in delete(odel_temp1) : could not find function "delete"
> detach(odel_temp1)
Error in detach(odel_temp1) : invalid 'name' argument
> summary(model_temp1)

Call:
lm(formula = INCWAGE ~ AGE + female + AfAm + Asian + Amindian + 
    race_oth + Hispanic + educ_hs + educ_somecoll + educ_college + 
    educ_advdeg)

Residuals:
   Min     1Q Median     3Q    Max 
-91473 -25294  -8679  12156 645990 

Coefficients:
                Estimate Std. Error t value Pr(>|t|)    
(Intercept)    26745.369    630.833  42.397  < 2e-16 ***
AGE             -189.515      8.038 -23.576  < 2e-16 ***
female        -17005.832    306.035 -55.568  < 2e-16 ***
AfAm           -5979.715    470.978 -12.696  < 2e-16 ***
Asian           -246.677    622.420  -0.396   0.6919    
Amindian       -4434.481   2531.131  -1.752   0.0798 .  
race_oth       -3473.873    572.419  -6.069 1.29e-09 ***
Hispanic       -1001.109    521.614  -1.919   0.0550 .  
educ_hs        11803.744    517.546  22.807  < 2e-16 ***
educ_somecoll  19141.373    557.270  34.348  < 2e-16 ***
educ_college   45536.173    570.431  79.828  < 2e-16 ***
educ_advdeg    68896.919    608.312 113.259  < 2e-16 ***
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

Residual standard error: 61590 on 163146 degrees of freedom
  (33427 observations deleted due to missingness)
Multiple R-squared:  0.1337,	Adjusted R-squared:  0.1337 
F-statistic:  2289 on 11 and 163146 DF,  p-value: < 2.2e-16

> plot(model_temp1
+ )

