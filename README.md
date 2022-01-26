# Simple-Regression-Analysis-with-R-in-built-Data.
This is an operation to make data slicing on in-built data frame in R and also performing simple regression analysis on them.
## Uthman's Assignment
## QUESTION 1
## load the in-built data USArrests
USArrests
attach(USArrests)
## exploring the data
?USArrests
## number of rows
nrow(USArrests)
## number of columns
ncol(USArrests)
head(USArrests)
summary(USArrests)
## subset Murder and Assualt
mur.ass <- USArrests[c('Murder','Assault')]
## regression for Murder and Assault
reg_mur.ass <- lm(Murder~Assault,mur.ass)
summary(reg_mur.ass)
## Interpretation
## The possible level of dependency between
## murder and assault can be expressed using the regression equation
## murder = 0.63 + 0.042*Assault where intercept = 0.63 and slope=0.042
## With significance =  2.596e-12 which is less than pvalue= 0.05, we conclude that
## the test is significant.
## with Adjusted R-squared:  0.6356, the Assault can account for 64% of the variation in murder.
##
## subset Murder and Urban population
mur.urban <- USArrests[c('Murder','UrbanPop')]
## regression for Murder and UrbanPop
reg_mur.urban <- lm(Murder~UrbanPop,mur.urban)
summary(reg_mur.urban)
## Interpretation
## The possible level of dependency between
## murder and urban population can be expressed using the regression equation
## murder = 6.42 + 0.021*UrbanPop where intercept = 6.42 and slope=0.021
## With significance =  0.6312 which is greater than pvalue= 0.05, we conclude that
## the test is not significant i.e Urban population do not determine significantly murder rate in the country
## with Adjusted R-squared:  -0.01589 , Urban Population can not account for the variation in murder.

## QUESTION 2
## load the in-built data mtcars
mtcars
## exploring the data
?mtcars
## number of rows
nrow(mtcars)
## number of columns
ncol(mtcars)
head(mtcars)
summary(mtcars)
## subset cylinders and horsepower
cyl.hp <-mtcars[c('cyl','hp')]
## regression for Murder and Assault
reg_cyl.hp <- lm(hp~cyl,cyl.hp)
summary(reg_cyl.hp)
## Interpretation
## The possible level of dependency between
## number of cylinder and gross horsepower of the cars
## can be expressed using the regression equation
## horsepower = -51.054 + 31.958*no_of_cylinders where intercept = -51.054 and slope=31.958
## With significance =  3.48e-09 which is less than pvalue= 0.05, we conclude that
## the test is significant.
## with Adjusted R-squared:  0.6827, the number of cylinders can account for 68% of the variation in horsepower of cars.
##
##
## subset cylinders and displacement
cyl.disp <-mtcars[c('cyl','disp')]
## regression for cylinders and displacement
reg_cyl.disp <- lm(disp~cyl,cyl.disp)
summary(reg_cyl.disp)
## Interpretation
## The possible level of dependency between
## number of cylinder and displacement moved by the cars
## can be expressed using the regression equation
## displacement = -156.609 +  62.599*no_of_cylinders where intercept = -156.609 and slope=62.599
## With significance = 1.8e-12 which is less than pvalue= 0.05, we conclude that
## the test is significant.
## with Adjusted R-squared:    0.8075, the number of cylinders can account for about 80% of the variation
## in displacement moved by cars.
##
