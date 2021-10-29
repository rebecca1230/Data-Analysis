Does the job training program increase real earning ?

library(MatchIt)
library(tidyverse)
data(lalonde)
```
summary(lm(re78 ~ treat + re75 (control_variables), data = lalonde))
```

CONFOUNDER
```
g = dagitty("dag{
      TREAT = INCOME78
      INCOME75 = TREAT
      INCOME75 = INCOME78
          }")
coordinates(g) = list(x = c(INCOME75 =3, TREAT =3, INCOME78 = 5),
                      y = c(INCOME75 =0, TREAT =1, INCOME78 = 1))
plot(g)
```
