# Class 4 Part 1 
## Plot
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

