# ECON-HW-4

Lab 4
```
> load("/cloud/project/acs2017_ny_data.RData")
> attach(acs2017_ny)

> model_temp1 <- lm(INCWAGE ~ su)

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

Linear Regression Plot with Y Limitations (please see attached) 

The Linear Regression Plot with Y Limitations shows income values relative to age evenly spaced out. 

````

> plot(INCWAGE ~ jitter(AGE, factor = 2), pch = 16, col = rgb(0.5, 0.5, 0.5, alpha = 0.2), ylim = c(0,150000), data = dat_graph)
> to_be_predicted2 <- data.frame(AGE = 25:55, female = 1, AfAm = 0, Asian = 0, Amindian = 1, race_oth = 1, Hispanic = 1, educ_hs = 0, educ_somecoll = 0, educ_college = 1, educ_advdeg = 0)

````
Linear Regression Plot with Income and Age- Please see attached 

Our Linear Regression Line shows a slightly negative sloping line hovering at around 49,000 at age 25 and decreasing to 45,000 dollars per year at around 55 years age . The ACS 2017 data looks at respondents from the entire new york state, which was surprising to find out that the median average income of 25 year olds in the data set was less than the national average which is 50,000. I believe that the population of respondents in the ACS dataset has skewed our regression to a lower income. It seems a typical respondent who answers the Census is probably somone who is older and as a result might be retired and making less than the national average. 

Homework 4:

For our Homwork we wanted to address the effects of gentrication in lower income neighborhoods particulary in NYCHA and then compare the data from the ACS 2017 values to see if their were any potential correlations. We referred to the article "Linking Residents to Opportuntity, Gentrification In Housing" by Samuel Dastrup and Ingrid Gould Ellen. 

In the article the author created a data set defining housing income in NYCHA communities as low, increasing and high.
Low was defined as 19,500
Increasing was defined as 20,698
High was defined as 21,648

`````

> load("/cloud/project/acs2017_ny_data.RData")
> attach(acs2017_ny)
> View(acs2017_ny)
> model_temp1 <- lm(HHINCOME ~ AGE + female + AfAm + Asian + Amindian + race_oth + Hispanic + educ_hs + educ_somecoll + educ_college + educ_advdeg + FAMSIZE  )
> summary(model_temp1)

Call:
lm(formula = HHINCOME ~ AGE + female + AfAm + Asian + Amindian + 
    race_oth + Hispanic + educ_hs + educ_somecoll + educ_college + 
    educ_advdeg + FAMSIZE)

Residuals:
    Min      1Q  Median      3Q     Max 
-297507  -59946  -24950   22929 1909729 

Coefficients:
               Estimate Std. Error
(Intercept)    68225.21    1114.90
AGE             -222.17      15.42
female         -8388.40     568.72
AfAm          -28547.11     892.60
Asian          -7226.23    1141.97
Amindian      -30117.99    4597.93
race_oth      -10928.95    1018.76
Hispanic      -24032.02     935.99
educ_hs         -782.10     900.21
educ_somecoll  13089.01     966.55
educ_college   61426.07     975.84
educ_advdeg   100206.97    1083.36
FAMSIZE        13955.76     179.87
              t value Pr(>|t|)    
(Intercept)    61.194  < 2e-16 ***
AGE           -14.406  < 2e-16 ***
female        -14.750  < 2e-16 ***
AfAm          -31.982  < 2e-16 ***
Asian          -6.328 2.49e-10 ***
Amindian       -6.550 5.76e-11 ***
race_oth      -10.728  < 2e-16 ***
Hispanic      -25.676  < 2e-16 ***
educ_hs        -0.869    0.385    
educ_somecoll  13.542  < 2e-16 ***
educ_college   62.947  < 2e-16 ***
educ_advdeg    92.496  < 2e-16 ***
FAMSIZE        77.590  < 2e-16 ***
---
Signif. codes:  
  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’
  0.1 ‘ ’ 1

Residual standard error: 122200 on 185942 degrees of freedom
  (10630 observations deleted due to missingness)
Multiple R-squared:  0.1113,	Adjusted R-squared:  0.1113 
F-statistic:  1941 on 12 and 185942 DF,  p-value: < 2.2e-16

````
To Keep in line with the orginal data set we used Household Income and added Family Size to the data set. 
`````


[GitHub](https://www-jstor-org.ccny-proxy1.libr.ccny.cuny.edu/stable/pdf/26328274.pdf?ab_segments=0%252Fbasic_search_SYC-5462%252Ftest&refreqid=excelsior%3A3df675c39d7997c6fdfbf151b566c4d5)




