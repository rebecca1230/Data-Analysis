# Class 4 Part 2 : Hypothesis Testing
## Section 1
1. quantile
2. quantile(x=draws,probs=c(0.25, 0.5, 0.75), na.rm)
+ probs is a sequence from 0 to 1 every 2.5

Draw histogram:
```
draws = rnorm(1000, mean = 0, sd =1)
hist(draws)
```
Quantile function:
```
quantile(x = draws, probs = 0.5)
(Get Median: The number at which 50% of the population is above and below that value.)
quantile(x = draws, probs = c(0.25, 0.5, 0.75))
(Get Median / Upper-quartile / Lower-quartile)
```
Add the quantile as vertical lines:
```
abline(v = quantile(x = draws, probs = c(0.25, 0.5, 0.75)),
       lwd = 2, lty = "dashed",
       col = "black")
```
Find where 95% of the value fall:
```
abline(v = quantile(x = draws, probs = c(0.025, 0.975)),
       lwd = 2, lty = "dashed",
       col = "grey")
```
Draw2 Histogram (mean changes from 0 to 0.5)
```
draws2 = rnorm(1000, mean = 0.5, sd = 1)
hist(draws2)
abline(v = quantile(x = draws2, probs = c(0.25, 0.5, 0.75)),
       lwd = 2, lty = "dashed",
       col = "black")
abline(v = quantile(x = draws2, probs = c(0.025, 0.975)),
       lwd = 2, lty = "dashed",
       col = "grey")
```
Compare Histograms draw & draw2
```
par(mfrow = c(2,1))

draws = rnorm(1000, mean = 0, sd =1)
hist(draws,
     xlin = c(-5,5))
abline(v = quantile(x = draws, probs = c(0.25, 0.5, 0.75)),
       lwd = 2, lty = "dashed",
       col = "black")
abline(v = quantile(x = draws, probs = c(0.025, 0.975)),
       lwd = 2, lty = "dashed",
       col = "grey")

draws2 = rnorm(1000, mean = 0.5, sd = 1)
hist(draws2)
abline(v = quantile(x = draws2, probs = c(0.25, 0.5, 0.75)),
       lwd = 2, lty = "dashed",
       col = "black")
abline(v = quantile(x = draws2, probs = c(0.025, 0.975)),
       lwd = 2, lty = "dashed",
       col = "grey")
```
+ xlin = c(-5,5) : Make x axis wider. x value range (-5,5)

## Section 2
1. Are these different distribution and data? 
2. Null : no difference  
3. Alternative : is a difference

Copy the CI functions from Class 4-1: 
```
conf.int99 = function(x) {
  mean(x) + 2.5 * std.error(x)
  mean(x) - 2.5 * std.error(x) 
  conf.int = c(mean(x) + 2.5 * std.error(x),
               mean(x) - 2.5 * std.error(x))
  return(conf.int)
}
conf.int99(x)

conf.int95 = function(x) {
  mean(x) + 1.97 * std.error(x)
  mean(x) - 1.97 * std.error(x) 
  conf.int = c(mean(x) + 1.97 * std.error(x),
               mean(x) - 1.96 * std.error(x))
  return(conf.int)
}
conf.int95(x)

conf.int90 = function(x) {
  mean(x) + 1.645 * std.error(x)
  mean(x) - 1.645 * std.error(x) 
  conf.int = c(mean(x) + 1.645 * std.error(x),
               mean(x) - 1.645 * std.error(x))
  return(conf.int)
}
conf.int90(x)

confidence.interval = function(x, confidence) {
     if(confidence == 0.90) {
        out = conf.int90(x)
     } else if(confidence == 0.95) {
        out = conf.int95(x)
     } else if(confidence == 0.99) {
        out = conf.int99(x)
     } else { 
        print("CI can only be 0.90, 0.95, 0.99")
        out = NA
     } 
     return(out)
}
```
How uncertain are we that the averages are actually different?
Get CI first: 
```
confint_draws1 = confidence.interval(x = draws, confidence = 0.95)
confint_draws2 = confidence.interval(x = draws2, confidence = 0.95)
confint_draws1
confint_draws2
```
Drawing the CIs onto the two Histograms:
```
par(mfrow = c(2,1))
hist(draws, xlim = c(-1,1))
abline (v = confint_draws1, 
        lwd = 2, col = "red")
hist(draws2, xlim = c(-1,1))
abline (v = confint_draws2, 
        lwd = 2, col = "red")
```
+ We see a significant statistical difference. No overlap of 95% CI for the two graphs. 

## Section 3 
1. Make draw and draws Histograms the same. 
+ *Go back to Section 1: "Compare Histograms draw & draw2" and change mean of draws2 from 0.5 to 0* 
```
draws = rnorm(1000, mean = 0, sd =1)
draws2 = rnorm(1000, mean = 0, sd =1)
```
2. Run the Analysis of whether 95% CI overlapps
```
confint_draws1 = confidence.interval(x = draws, confidence = 0.95)
confint_draws2 = confidence.interval(x = draws2, confidence = 0.95)
````
+ Do overlap. 

### Make the data easier to read
Reduce the number of draws creates wider CI better for observe: 
```
draws = rnorm(100, mean = 0, sd =1)
draws2 = rnorm(100, mean = 0.1, sd =1)
```
## Section 4: Simplify our method
Use the difference of the histograms to check:
```
difs = draws - draws2
hist(difs, xlim = c(-5,5), breaks = 10) 
abline(v = confidence.interval(difs, 0.95), lwd = 2)
```
+ Take the histogram of dif 
+ Clear the previous histogram with dev.off() in console
+ Conclude CI overlaps or not. 

## Section 5: t-test 
### Two Sample t-test
t.test(x = draws, y = draws2)
+ y does not need to exist. 
+ If y does not exist, it is assumed that we are comparing x and 0.
+ Welch Two Sample t-test: Provided both x & y.
+ **Chances of there is no difference (null hypothesis is true) gets lower as p-value gets smaller. 
+ **A p-value < 0.05 rejects the null hypothesis (the idea of no difference gets rejected).
### One Sample t-test
```
t.test(x=difs)
```
## Notes
1. dev.off() : Clear. 
2. *breaks*
3. Power calculation
