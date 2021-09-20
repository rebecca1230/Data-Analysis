# Class 4 Part 1 
## Exercise 1: Plot
Plot 500 draws of a normal distribution with mean 3 sd 1.5. 
```
rnorm(n=500, mean=3, sd =1.5)

hist(rnorm(n=500, mean=3, sd =1.5), 
     xlab = "Normal Draws", 
     main = "500 Draws from a Normal(3, 1.5)")
```
Plot 500 draws of a uniform distribution from 0 to 6. 
```
runif(n = 500,
      min = 0,
      max = 6)
      
hist(runif(n = 500,
      min = 0,
      max = 6),
      xlab = "Uniform Draws",
      main = "500 Draws from a Uniform (0,6)")
```
Combine the two graphs
par(mfrow=c(nr,nc)) : (nr,nc)= (1,2) means 1 row 2 column ; 2 plots side by side.
```
par(mfrow=c(1,2))

hist(runif(n = 500,
      min = 0,
      max = 6),
      xlab = "Uniform Draws",
      main = "500 Draws from a Uniform (0,6)")

hist(rnorm(n=500, mean=3, sd =1.5), 
     xlab = "Normal Draws", 
     main = "500 Draws from a Normal(3, 1.5)")
```
*dev.off*

## Exercise 2: Function of Confidence Intervals 
1. x = rnorm(n=500, mean =3, sd=1.5)
2. library(plotrix) 
3. plotrix::stderror
4. mean(x) + 1.97 (asterisk) std.error(x)
5. mean(x) - 1.97 (asterisk) std.error(x)
```
conf.int99 = function(x) {
    mean(x) + 2.5 (asterisk) std.error(x)
    mean(x) - 2.5 (asterisk) std.error(x) 
    conf.int = c(mean(x) + 2.5 (asterisk) std.error(x),
                 mean(x) - 2.5 (asterisk) std.error(x))
    return(conf.int)
}
conf.int99(x)
```
## Combine functions 
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

confidence.interval(x, confidence =0.99)
```
