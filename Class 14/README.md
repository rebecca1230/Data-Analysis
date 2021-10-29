# Match it and Covariant balance

library(MatchIt) \
library(tidyverse) \
data(lalonde)

1. re78 is Real Earnings in 1978.
2. Outcome(Dependent variable): How much money(real dollars) did the respondents earn in 1978? 
3. Independent variable: treat(job training program)
4. Does the job training program increase real earning ?

(Linear Regression) Evaluate the impact of millions of government's money:
```
summary(lm(re78 ~ treat, data = lalonde))
```
+ Based money is 6984
+ -635 means people who took the job training progam earn less thatn those who did not attend the job training program. 

DAG:
```
g = dagitty("dag{
      TREAT -> INCOME78 (maybe this correlation does not exist)
      INCOME75 (CONFOUNDER) -> TREAT
      INCOME75 (CONFOUNDER) -> INCOME78
          }")
coordinates(g) = list(x = c(INCOME75 =3, TREAT =3, INCOME78 = 5),
                      y = c(INCOME75 =0, TREAT =1, INCOME78 = 1))
plot(g)
```
Control Variables: 
1. "summary(lm(re78 ~ treat," means obversing the effect treat(independent variable) has on re78 (dependent variable). 
2. We notice a negative relationship between treatment and real earnings in 1978.
3. It is weird to see that people who go through the job training program earn less than those who did not do the job training program. 
4. We suspect factors besides treat caused this result:
```
summary(lm(re78 ~ treat + re75 (control_variables), data = lalonde))
summary(lm(re78 ~ treat + age + nodegree + married + educ + re4 + re5, data = lalonde))
```
+ When we control for other factors, we observe that there is a positive relationship between re78 and treat. 

```

```
