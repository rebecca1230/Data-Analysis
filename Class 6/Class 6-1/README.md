# Class 6 Part 1: Regression
## Math
If we list all the whole positive numbers below 10 that are mutiples of 3 or 5, we get 3,5,6,9. The sum of these mutiples is 23. 
[QUESTION] Find the sum of all the mutiples of 3 or 5 below 1000.
```
10 %% 3 
```
+ %% gets us the remainder. 

[1] If a value is a multiple of 3 or 5, meaning 10 %% 3 == 0 OR 10 %% 5 == 0, then add the value to the list "out"
```
x = 1: 999
out = c()
for( i in 1:length(x) ) {
  if (i %% 3 == 0 | i %% 5 == 0) {
   out = c(out,i)
  } 
  print(i)
}
sum(out)
```
[2] Make the above into one line of code: 
```
x[x %% 3 == 0 | x %% 5 == 0]
```
+ This idea of subset in above is that TRUE | FALSE generates TRUE 
+ For the values in x that get the result TRUE after running the line of code, we add them to the list. 
```
sum(x[x %% 3 == 0 | x %% 5 == 0])
```
+ We get the same result as using the for loop.

## Types of Data
1. Binary (zero OR 1)
```
rbinom(1000, 1, 0.5)
```
2. Categorical
```
sample(1:5, 10, replace = F)
sample(c("blonde", "brunette", "redhead", "rainbow"), 10, replace = T)
```
+ Gets a vector of 10 random head colors.

3. Ordinal

4. Continuous 
runif(100)
rnorm()
+ pi is a continuous number

5. Count 
rbinom(1000, 5, 0.5)
hist(rpois(100,1))
+ Continuous numbers in integers.

## Note & Questions
1. TRUE | FALSE | FALSE | FALSE = TRUE
2. TRUE & FALSE & FALSE & FALSE = FALSE
3. for loops in R can be slow ; R prefers vector.
4. With continuous & Count numbers, we can make comparisons.
5. What is replace for? 

