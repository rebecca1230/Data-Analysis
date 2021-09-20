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

Copy the CI function from Class 4-1: 
```
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
```
confint_draws1 = confidence.interval(x = draws, confidence = 0.95)
confint_draws2 = confidence.interval(x = darws2, confidence = 0.95)
```

4. 
