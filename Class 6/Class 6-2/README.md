# Class 6 Part 2 : Regression 
## [1] Check correlation
Dependent and independent variables.
```
data("USArrests")
plot(x = USArrests$Murder,
     y = USArrests$Assault,
     xlab = "Murders",     
     ylab = "Assaults",
     pch = 16, cex = 1.5)
cor(x = USArrests$Murder,
    y = USArrests$Assault)
```
## [2] Line
y = bx + a 
```
abline(a = 100,
       b = 10, col = "red")
```
The line of best fit
```
lm(data,formula tell R what de/in are)
lm(data = USArrests, 
   formula = "Assault ~ UrbanPop")
             [dependent]~[independent]
```
## Note & Question
1. cex is size. 
2. I have a different plot. 
