# Class 6 Part 2 : Regression 
## Check correlation
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
## Line
### y = bx + a 
```
abline(a = 100,
       b = 10, col = "red")
```
### Find a & b
```
lm(data,formula tell R what de/in are)

lm(data = USArrests, 
   formula = "Assault ~ UrbanPop")
   
             [dependent]~[independent]
             explain assault rate using urban population.
```
+ Run the code and we get: 
+ (1) Call: lm(formula, data). Call changes the argument order.
+ (2) Coefficients: a = Intercept / b = UrbanPop

### Draw the line of best fit 
For Assault and Murder:
```
lm(data = USArrests, 
   formula = "Assault ~ Murder")
abline(a = 51.27,
       b = 15.34, col = "red")
```


## Note & Question
1. cex is size. 
2. I have a different plot. 
