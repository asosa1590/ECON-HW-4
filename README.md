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

`````

Please see attached Linear Regression Plot

Stargazer Model
````
> require(stargazer)
> stargazer(model_temp1, type = "text")

==================================================
                         Dependent variable:      
                    ------------------------------
                               INCWAGE            
--------------------------------------------------
AGE                          -189.515***          
                               (8.038)            
                                                  
female                      -17,005.830***        
                              (306.035)           
                                                  
AfAm                        -5,979.715***         
                              (470.978)           
                                                  
Asian                          -246.677           
                              (622.420)           
                                                  
Amindian                     -4,434.481*          
                             (2,531.131)          
                                                  
race_oth                    -3,473.873***         
                              (572.419)           
                                                  
Hispanic                     -1,001.109*          
                              (521.614)           
                                                  
educ_hs                     11,803.740***         
                              (517.546)           
                                                  
educ_somecoll               19,141.370***         
                              (557.270)           
                                                  
educ_college                45,536.170***         
                              (570.431)           
                                                  
educ_advdeg                 68,896.920***         
                              (608.312)           
                                                  
Constant                    26,745.370***         
                              (630.833)           
                                                  
--------------------------------------------------
Observations                   163,158            
R2                              0.134             
Adjusted R2                     0.134             
Residual Std. Error    61,589.210 (df = 163146)   
F Statistic         2,289.331*** (df = 11; 163146)
==================================================
Note:                  *p<0.1; **p<0.05; ***p<0.01

`````
Linear Regression Plot without Y Limitations (please see attached) 

The Linear Regression Plot is highly skewed to the bottom portion of the graph , the reason for this is because we have not created a Y Limitation in our code.

````







