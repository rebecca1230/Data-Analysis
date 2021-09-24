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
### Muti-variable Regression
```
m = lm(data = USArrests, 
   formula = " Murder ~ Assault + UrbanPop ")
               [y axis] ~ [x axis] + [z axis]
summary(m)
```
+ y = bx + a
+ y = bi* Assault + b2* UrbanPop + a 
+ y = [x axis] + [z axis] + a 
+ After running the code summary(m):
+ Assault has + coefficient ; UrbanPop has - coefficient
+ Two cities with same Assault rate, the one with lower UrbanPop will have slightly higher Murder rate (negative relationship).
+ Increase Assault rate by 1, then we are increasing the Murder rate by 0.043910. 
+ Increase the independent variable by 1, holding other indepedent variables constant, then the dependent variable will be increased by the estimate value.  


## Note & Question
1. cex is size. 
2. I have a different plot. 
