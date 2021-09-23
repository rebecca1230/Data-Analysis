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
### Using the dollar sign
england[ "the rows of which the home column is Arsenal" , "display column hgoal" ]
```
england[england[,"home"]== "Arsenal" , "hgoal"]
```
(for england data set's hgoal column)[(give me the ones that their home column is "Arsenal")]
```
england$hgoal[england$home == "Arsenal" ]
```
+ engalnd$hgoal is a vector and not data frame ; subset it with a logical vector [england$home == "Arsenal" ].
+ This works only cuz the length of the logical vector[england$home == "Arsenal" ] is the same as england$hgoal.
```
x = c(1,2,3)
x[c(TRUE, TRUE, FALSE)]
```
+ Run the above and get 1,2

Two different ways to answer Arsenal's performance at home and away:
```
england[england[,"home"]== "Arsenal" , "hgoal"]
england$hgoal[england$home == "Arsenal" ]

england[england[,"visitor"]== "Arsenal" , "vgoal"]
england$vgoal[england$visitor == "Arsenal" ]
```
