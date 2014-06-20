---
title       : How long is a criminal's middle finger
subtitle    : Developing Data Products Project
author      : Ye Wang
job         : Master student in Management Information System
logo        : UMD-Smith-Black.png
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : [shiny]            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
---

## Description

1. The application is for fun. But the experiment is famous, you can find the essay called "identification of criminals"
2. The original dataset contained data of 3000 male criminals over 20 years old undergoing their sentences in the chief prisons of England and Wales
3. Processed original data into data frame with 3000 rows and 3 columns
4. Three variables were 'type', 'height.cm' and 'middle.finger.cm'. The last variable was the dependent variable 
5. Built linear regression model by using criminals' height to predict their length of middle finger


```r
data(crimtab)
```

--- .class #id 

## Data Processing

Following is the first ten rows of processed data frame for the dataset. 


```
##        type height.cm middle.finger.cm
## 1  criminal     157.5             11.8
## 2  criminal     177.8             12.8
## 3  criminal     165.1             11.3
## 4  criminal     157.5             11.3
## 5  criminal     177.8             12.7
## 6  criminal     160.0             11.9
## 7  criminal     160.0             11.7
## 8  criminal     162.6             10.9
## 9  criminal     165.1             11.3
## 10 criminal     167.6             11.2
```

---

## Model Evaluation


```r
model <- lm(middle.finger.cm~height.cm,data=crimtab_edited)
summary(model)
```

```
## 
## Call:
## lm(formula = middle.finger.cm ~ height.cm, data = crimtab_edited)
## 
## Residuals:
##     Min      1Q  Median      3Q     Max 
## -1.9689 -0.2842  0.0005  0.2752  1.5785 
## 
## Coefficients:
##             Estimate Std. Error t value Pr(>|t|)    
## (Intercept)  2.33739    0.19383    12.1   <2e-16 ***
## height.cm    0.05538    0.00116    47.5   <2e-16 ***
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
## 
## Residual standard error: 0.414 on 2998 degrees of freedom
## Multiple R-squared:  0.43,	Adjusted R-squared:  0.43 
## F-statistic: 2.26e+03 on 1 and 2998 DF,  p-value: <2e-16
```


---

## Application

Please go to the https://jasonwang.shinyapps.io/ShinyProject/ to use the application. 

Loading might be slow, please be patient.

There are specific documentation in the app website. Thank you.


