# Simple-Regression-Analysis-with-R-in-built-Data.
This involves an operation to make data slicing on in-built data frames in R and perform Simple Regression Analysis.


## Data Ingestion

```r
load the in-built data USArrests
USArrests
attach(USArrests)
```

## Exploring the data

We first start by checking the number of rows

```r
## number of columns
nrow(USArrests)
```

then the number of columns

```r
ncol(USArrests)
head(USArrests)
```
Then it's necessary to perform an actual EDA (Exploratory Data Analysis)

```r
summary(USArrests)
## subset Murder and Assualt
```

concatenating the needed dataframe

```r
mur.ass <- USArrests[c('Murder','Assault')]
```

Onto the actual regression model

## Regression for Murder and Assault

```r
reg_mur.ass <- lm(Murder~Assault,mur.ass)
```

The summary of the regression analysis results

```r
summary(reg_mur.ass)
```

**Interpretation:** The possible level of dependency between murder and assault can be expressed using the regression equation


murder = 0.63 + 0.042*Assault where **intercept** = 0.63 and **slope** = 0.042


With significance =  2.596e-12 which is less than pvalue= 0.05, we conclude that the test is significant.

With Adjusted R-squared:  0.6356, the Assault can account for 64% of the variation in murder.

_________________________________

For subset Murder and Urban population
```r
mur.urban <- USArrests[c('Murder','UrbanPop')]
```

## Regression for Murder and UrbanPop

```r
reg_mur.urban <- lm(Murder~UrbanPop,mur.urban)
```

Finding the summary

```r
summary(reg_mur.urban)
```

**Interpretation:** the possible level of dependency between murder and urban population can be expressed using the regression equation

murder = 6.42 + 0.021*UrbanPop where **intercept** = 6.42 and **slope** =0.021 with **significance** =  0.6312 which is greater than **p-value** = 0.05, we conclude that the test is not significant i.e **Urban population** do not significantly determine murder rate in the country, with **Adjusted R-squared:**  -0.01589 , Urban Population can not account for the variation in murder.


## QUESTION 2

## Data Ingestion

load the in-built data mtcars

```r
mtcars
```

## Exploring the data

number of rows
```r
nrow(mtcars)
```

```r
ncol(mtcars)
head(mtcars)
summary(mtcars)
```


subset cylinders and horsepower
```{r}
cyl.hp <-mtcars[c('cyl','hp')]
```

## Regression for Murder and Assault

```r
reg_cyl.hp <- lm(hp~cyl,cyl.hp)
summary(reg_cyl.hp)
```

**Interpretation:** The possible level of dependency between number of cylinder and gross horsepower of the cars can be expressed using the regression equation  **horsepower** = -51.054 + 31.958*no_of_cylinders where **intercept** = -51.054 and slope=31.958 with **significance** =  3.48e-09 which is less than **pvalue** = 0.05, we conclude that the test is **significant**.

with Adjusted **R-squared:  0.6827,** the number of cylinders can account for 68% of the variation in horsepower of cars.

Subset cylinders and displacement

```r
cyl.disp <-mtcars[c('cyl','disp')]
```

## Regression for cylinders and displacement

```r
reg_cyl.disp <- lm(disp~cyl,cyl.disp)
summary(reg_cyl.disp)
```


**Interpretation:** The possible level of dependency between number of cylinder and displacement moved by the cars can be expressed using the regression equation

displacement = -156.609 +  62.599*no_of_cylinders where **intercept** = -156.609 and **slope** =62.599


**With significance** = 1.8e-12 which is less than **pvalue** = 0.05, we conclude that the test is significant. With **Adjusted R-squared:** 0.8075, the number of cylinders can account for about 80% of the variation in displacement moved by cars.
