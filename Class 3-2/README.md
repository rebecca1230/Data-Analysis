# Class 3 Part 2
1. install.packages("mosaic")
2. install.packages("plotrix")
3. library(mosaic)
4. library(plotrix)
5. dat = MASS::survey
```
plot(x = dat[, "Wr.Hnd"], 
     y = dat[,"NW.Hnd"], 
     xlab = "Writing Hand Width (cm)",
     ylab = "Non-Writing Hand Width (cm)"
     main = "Writing vs Non-Writing Hand Width",
     pch = 16, 
     col = "firebrick3"
     )
```
+ pch : point characteristics (solid circle/upside-down triangle/etc)
+ col : colors of the points EX: dodgerblue2

```
hist(x = dat[, "Wr.Hnd"], 
     xlab = "Writing Hand Width (cm)",
     main = "Histogram of Writing Hand Width",
     breaks = 20)
```
+ y means the Frequency (number of values for each x)
+ breaks : the number of bars.

```
mean(dat[, "Wr.Hnd"], na.rm=TRUE)
```
Add average onto the plot: 
```
abline(v = mean(dat[, "Wr.Hnd"], na.rm=TRUE), lwd = 2, lty = "dashed", col = "grey")
```
+ v : vertical line
+ lwd : line width 
+ lty : line type

## Confidence Interval: Quantify the uncertainty about the true population
1. x = dat[, "Wr.Hnd"]
2. sd(x, na.rm =TRUE)
3. 

