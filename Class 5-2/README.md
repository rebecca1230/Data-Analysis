# Class 5 Part 2

## Does the lady know tea/milk first? 
1. Null hypothesis: (no ability) The lday gets wrong the same number she gets right.
2. Alternative hypothesis (yes ability): More rights than wrongs. 
3. How many rights do we need? 
4. (For 4 tea first 4 milk first) If guessed 5 rights, we still can not conclude she has this ability, as she might just get lucky. 
5. (For 4 tea first 4 milk first) If she gets 8 rights, she is pretty likely to have the ability, but how likely is it? 
6. (For 4 tea first 4 milk first) If she gets zero right, that is the same as getting eight right. 8 right and 0 right has the same probability: Both means she has the ability. 
7. Getting 100% and getting 0% on a multiple choice test both means we might know all the answer. 

## Bionmial Distribution of testing
[1] Taste one cup of tea (n = 1 / draw = 1) from the given 8 cups (size = 8). 
```
rbinom( n = 1, size = 8, prob = 0.5)
```
+ Outcome of this code is one value that is between 0 & 8.
+ All together shows the distribution of the numbers of tea she'll get right under the null hypothesis (no ability). 

[2] Let her taste the tea for 1000 times:
```
rbinom( n = 1000, size = 8, prob = 0.5)

```
[3] See what the distribution is like under histogram: 
```
hist(rbinom( n = 1000, size = 8, prob = 0.5))
```
[4] The number of times she'll get 0,1,2,3,4,5,6,7,8 cups right in the 1000 times:
```
table(rbinom( n = 1000, size = 8, prob = 0.5))
```
[5] In 95% of the times we test her, what is the number that she'll get it right?
```
tests = rbinom( n = 1000, size = 8, prob = 0.5)
quantile(tests, probs = c(0.025, 0.975))
```
+ 95% of the data, she gets between 1 & 7 correct. 
+ How many successes shes needs for us to reject the null ? 
+ ANSWER: 8, if we are looking for 95% CI, since 8 is outside of the 95% CI. 
+ In other words, she has to get all correct. 

[6] What if we increase the size by 2? 
```
tests = rbinom( n = 1000, size = 10, prob = 0.5)
quantile(tests, probs = c(0.025, 0.975))
```
+ She needs 9 or 10 correct for us to reject the null.
+ In other words, she does not need to get all correct. She can make one mistake. 

[7] Rather than having the null hypothesis to be she's guessing 50% 50%, let's change the null hypothesis to "she can get 60% or fewer of the time."
```
tests = rbinom( n = 1000, size = 10, prob = 0.6)
quantile(tests, probs = c(0.025, 0.975))
```
+ She needs to get it all right for us to say she could get it correct 60% of the time. 

# Notes & Question
1. Why 100% and 0% both means we know the answer ? 
2. [9:28] Why you know 0.5% of times, she gets it all right or all wrong?
