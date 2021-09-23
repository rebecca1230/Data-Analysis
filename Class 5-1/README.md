# Class 5 Part 1
## Exercise 1 
Take 1000 draws from the XYZ distribution:
```
par(mfrow = c(2,2))
hist(rnorm(1000), main = "Normal Draws")
hist(runif(1000), main = "Uniform Draws")
hist(rexp(1000), main = "Exponential Draws")
hist(rpois(1000, lambda=1), main = "Poisson Draws, lambda = 1")
```
## Exercise 2
Load engsoccerdata:
```
library(engsoccerdata)
data("england")
head(england)
```
### Run a t-test
```
england[ "Arsenal" , "home" ] : Arsenal's performance when it's home.
england[,"home"] EQUALS TO england$home
england$hgoal[england$home == "Arsenal"]
```
engalnd$hgoal is a vector and not data frame ; subset it with a logical vector.
This works only cuz the length of the logical vector is the same as the hgoals.
```
x = c(1,2,3)
x[c(TRUE, TRUE, FALSE)]
```
+ Run the above and get 1,2

