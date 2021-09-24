# Class 6 Part 2 : Regression 
## Check correlation
+ Dependent and independent variables.
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
lm(data,formula = tell R what dependent and independent variables are)

lm(data = USArrests, 
   formula = "Assault ~ UrbanPop")
   
             [dependent]~[independent]
             explain assault rate using urban population.
```
+ Run the code and we get: 
+ (1) Call: lm(formula, data). Call changes the argument order.
+ (2) Coefficients: a = Intercept ; b = UrbanPop

### Draw the line of best fit 
For Assault and Murder:
```
lm(data = USArrests, 
   formula = "Assault ~ Murder")
abline(a = 51.27,
       b = 15.34, col = "red")
```
### Make Prediction
1. y = b * x + a
2. Assaults = 15.34 * Murder + 51.27
3. Murder = 10 
4. 15.34 * 10 + 51.27 = Assault rate is 204.67

Get summary: 
```
m = lm(data = USArrests, 
   formula = "Assault ~ Murder")
summary(m)
```
+ Residuals is the distance from points to the line of best fit. 
+ Default null hypothesis is b = 0.

Predict Assault rates when Murder rates are 0,10,100: 
```
predict(m, data.frame(Murder = c(0, 10, 100)))
```


## Note & Question
1. cex is size. 
2. I have a different plot. 
