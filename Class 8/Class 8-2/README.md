# Class 8 Part 2 : Interaction effects

Interactions: 
1. We want the effect of some variable (relationship between x and y) to depend on the level of another. 
2. For example: More x might be more y if some variables are zero.

## Types:
1. Bivariate: y = a + b * x
2. Multivariate Regression: y = a + (b1 * x1) + (b2 * x2)
3. Interactions: y = a + (b1 * x1) + (b2 * x2) + b3 * (x1 * x2)

## Examples: 

Meat Consumption:
1. More educated people tend to be vegetarians. 
2. Religion can effect that too. 
3. (?) Amoung the most educated, there might be a strong relationship between Christian and meat consumption. 

Facebook: 
1. Women are on facebook more than men.
2. Democrats and Republican equally go on Facebook.
3. (?) Amoung Republicans, women are less likely to be on Facebook.

## Civil War 
1. Civil wars might are less likely to happen in democracy and rich countries.
2. How does democracy and GDP interact in generating civil wars? 
3. Hypothesize: In the poor countries, democracy does not reduce civil war. In the rich countries, democracy helps a lot in preventing civil war. 

Fake data set
```
set.seed(12345)
lgdp = runif(1000) * 3 + 7 
democ = (runif(1000) * lgdp/10) > 0.5
cor(democ,lgdp)
```
+ set.seed: Getting the same number.
+ lgdp: Creating fake GDP per capita values (uniform distribution from 3 to 7)
+ 1000: Hypothetical number of countries. 
+ runif(1000) * lgdp/10 : Richer countries are more likely to be democracies.
+ 0.5 : the bar for determining whether democray or not. > 0.5 is a democ ; < 0.5 is not a democ

Estimate each countries' hidden propability for civil war. 
```
prob = 0 + -0.1 * lgdp + 3.2 * democ + -0.4 * lgdp * democ + rnorm(1000)
```
+ y = a + (b1 * x1) + (b2 * x2) + b3 * (x1 * x2)
+ b1 = -0.1
+ b2 = 3.2
+ b3 = -0.4
+ *The latent probability risk.*

```
civwar = prob > 0
```
