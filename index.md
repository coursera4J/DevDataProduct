---
title       : Build Motor Trend Data Regression Model
subtitle    : Course Project for Developing Data Products
author      : 
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : prettify  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## About the dataset (mtcars)
* The data was extracted from the 1974 Motor Trend US magazine, and comprises fuel consumption and 10 other features for 32 automobiles (1973–74 models).
* 11 data columns representing fuel comsumption (mpg) and other aspects of automobile design and performance.


```
##  [1] "mpg"  "cyl"  "disp" "hp"   "drat" "wt"   "qsec" "vs"   "am"   "gear"
## [11] "carb"
```

* Question to Answer: How an individual feature may impact the fuel consumption?
* Can we come up with a model to predict the impact?

---

## Exploratory data analysis with plots
* Relationshps of Fuel Consumption with: "number of cylinders", "transmission type", "horsepower", and "weight".

![plot of chunk unnamed-chunk-2](assets/fig/unnamed-chunk-2.png) 

--- 

## Build Linear Regression Model with R
* The exploratory data analysis indicates a linear relatonship might exist, for example, between the fuel consumption (mpg) and the weight (wt).

* R provides a function (i.e. "lm") to easily build a linear regression model.


```r
wtModel<-lm(mpg~wt, data=mtcars)
wtModel$coefficient
```

```
## (Intercept)          wt 
##      37.285      -5.344
```


---

## Plot the Regression Model
* R also provides easy ways to visulize the regression model.
* Here is an example of using ggplot to plot the linear regression model.

```r
qplot(wt, mpg, data=mtcars, geom=c("point", "smooth"), method="lm")
```

![plot of chunk unnamed-chunk-4](assets/fig/unnamed-chunk-4.png) 
