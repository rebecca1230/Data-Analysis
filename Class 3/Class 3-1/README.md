 # Class 3 Part 1
## The difference between bracket notations
1. () Functions 
2. [] Subsetting
3. {} Conrtol flow : if/when/while
## Exercise 1 
1. Load a data: data("USArrests") 
2. < Environment > USArrests < Promise >
+ Promise: Data is there but not yet called.
3. View the 1st 10 rows: (a) USArrests[1:10,] (b) head(USArrests,n=10)
4. Texas's urban population: USArrests["Texas","UrbanPop"]
5. rownames(USArrests) : Texas is at 43rd row.
6. Sate with the highest murder rate: 
+ max(1,2,3) = 3
+ max(USArrests[, "Murder"])
```
rownames(USArrests[  USArrests [ , "Murder"] == max(USArrests[, "Murder"]) ,  ])
```
7. States with an UrbanPop greater than 60: 
```
USArrests[, "UrbanPop"] > 60 (Gives TRUE & FALSE)
USArrests[USArrests[, "UrbanPop"] > 60 , ] (Gives the rows having that TRUE)
sum(USArrests[, "UrbanPop"] > 60) (Total amount of TRUE)
```
8. Average assault rate for those States: 
```
mean(USArrests[ USArrests[, "UrbanPop"] > 60 , "Assault" ])
```
## Exercise 2
1. dat = MASS::survey 
+ Looking within in the MASS library, find the object call survey and put it under the environment "dat".
2. Take the first 4 rows: (a) dat[1:4,] (b) head(dat,n=4)
3. Average pulse rate of the female students: 
```
mean(dat[ dat[, "sex"] == "Female" , "Pulse" ], na.rm = TRUE) 
```
+ na.rm=TRUE ignores the N/A values.
