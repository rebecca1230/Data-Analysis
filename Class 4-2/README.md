# Class 4 Part 2 : Hypothesis Testing
1. quantile
2. draws = rnorm(1000, mean = 0, sd =1)
3. hist(draws)
4. quantile(x=draws,probs=c(0.25, 0.5, 0.75))
5. hist(draws)
6. abline( v = quantile(x=draws,probs=c(0.25, 0.5, 0.75)) )
