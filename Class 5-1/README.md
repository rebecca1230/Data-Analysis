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
### T-test
Use both x & y. x = Arsenal's home goals ; y = Arsenal's away goals.
```
t.test(x = england$hgoal[england$home == "Arsenal" ] ,
       y = england$vgoal[england$visitor == "Arsenal" ])
```
+ The difference between means of x&y (2.02 and 1.33) seems big. 
+ We don't know how uncertain(confidence interval) is. 
+ If CI overlaps 0, then we can not reject the null (can not reject this idea of there is no difference.)
+ 95% CI is 0.603 to 0.769 
+ CI is far away from 0.
```
t.test(x = england$hgoal[england$home == "Arsenal" ] ,
       y = england$vgoal[england$visitor == "Arsenal" ],
       conf.level = 0.99999999)    
```
+ Add more 9s to stregnthen the confidence.
+ We require so many 9s before CI looks like overlap 0. 
+ Thus, we conclude there is a statistical differences. 

### Compare Arsenal and Liverpool
```
t.test(x = england$hgoal[england$home == "Arsenal" ] ,
       y = england$hgoal[england$home == "Liverpool" ],
       conf.level = 0.95)  
```
+ CI overlpas 0 ; can not reject the null hypothesis. 
+ It is possible that there is no difference. 

# Notes & Questions 
1. Why is that CI has to be away from 0 ?
