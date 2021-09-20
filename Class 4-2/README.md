# Class 4 Part 2 : Hypothesis Testing
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
Draw2 Histogram
```
draws2 = rnorm(1000, mean = 0.5, sd = 1)
hist(draws2)
abline(v = quantile(x = draws2, probs = c(0.25, 0.5, 0.75)),
       lwd = 2, lty = "dashed",
       col = "black")
abline(v = quantile(x = draws2, probs = c(0.025, 0.975)),
       lwd = 2, lty = "dashed",
       col = "grey")
