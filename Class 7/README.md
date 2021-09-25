# Class 7

## Math Problem
1. (1^2 + 2^2 + ... + 10^2) = 385
2. (1 + 2 + ... + 10)^2 = 3025
3. 3025 - 385 = 2640
Calculate the above but replace 10 with 10000: 
```
(1:5)^2 
sum((1:10000)^2)
sum(1:10000)^2 - sum((1:10000)^2)
```
## tidyverse
```
install.packages("tidyverse")
install.packages("nycflights13")

library(tidyverse)
library(nycflights13)
dat = nycflights13::flights
view(dat)
```
Tie functions together: 
```
dat %>% function() %>% function() 
```
## tidyverse cheetsheet
1. filter() : Subsetting by rows.
2. select() : Subsetting by columns.
3. summarize() : Calculating a statistic based on a row of column.
4. mutate() : Generate a new column.
5. group_by() : *Select a variable ; break the dataset.*
6. arrange() : Reordering
7. desc() : Reorder by desceding. (Reverse order)
+ There are tidyverse cheat sheets avaiable. 

### Q1: All flights originating in JFK:
```
nrow(dat[dat$origin == "JFK",])
---------------------tidyverse-----------------------
dat %>% filter(origin == "JFK)

```
### Q2: The departure delay time of all flights by United Airlines(UA):
```
dat$dep_delay[dat$carrier == "UA"]
dat[dat$carrier == "UA", "dep_delay"]
---------------------tidyverse-----------------------
dat %>% 
  filter(carrier == "UA") %>% 
  select(dep_delay)
```
### Q3: The average delay of all flights from Newark and JFK together: 
```
mean(dat$dep_delay[dat$origin == "EWR" | dat$origin == "JFK"], na.rm=T)

mean(dat[ dat$origin == "EWR" | dat$origin == "JFK" , "dep_delay" ])
mean(dat[dat$origin %in% c("EWR","JFK"), "dep_delay"], na.rm=T)
---------------------tidyverse-----------------------
dat %>% 
  filter(origin %in% c("EWR","JFK")) %>%
  select(dep_delay) %>%
  summarize(mean(dep_delay, na.rm =T))
```
+ dat$origin %in% c("EWR","JFK")
+ EQUALS 
+ dat$origin == "EWR" | dat$origin == "JFK"

### Q4: The average delay of all flights from EWR, JFK ... individually: 
```
avg_delay_data = dat %>% 
  group_by(origin) %>%
  summarize(ave_delay = mean(dep_delay, na.rm =T ))
```
### Q5: Calculate the speed of all flights and order by speed:
```
dat$speed = dat$distance/dat$air_time
dat[order(dat$speed),]
---------------------tidyverse-----------------------
flight_speed = dat %>%
  mutate(speed = distance/air_time) %>%
  dplyr::arrange(desc(speed))
view(flight_speed)
```
### Q6: Keep only the variables year through tailnum 
```
dat[,1:12]
tailnum_id = which(colnames(dat) == "tailnum")
dat[, 1:tailnum_id]
---------------------tidyverse-----------------------
dat %>%
  select(year:tailnum)
```

## engsoccerdata [32:41]

### Q1: Which team has the highest total number of home goals scored? Hint: group_by, arrange
### Q2: Which team has the highest total number of goals allowed at home? 
### Q3: How many games has each team played as the home team ? Hint: n()

+ Next lecture: Regression Part 2

## Notes & Questions
1. mean does not work in Q3. 
2. function which: Tells us which element of a logical vector is TRUE or FALSE.
