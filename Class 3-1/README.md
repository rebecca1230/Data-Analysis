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
7. States with an UrbanPop greater than 60: USArrests[, "UrbanPop"] > 60
8. Average assault rate for those States: mean(USArrests[ USArrests[, "UrbanPop"] > 60 , "Assault" ])
