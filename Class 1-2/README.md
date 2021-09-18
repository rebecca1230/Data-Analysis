# Class 1 Part 2
## Install Packages
1. < Script > install.packages("engsoccerdata")
+ Successfully downloaded packages
3. < Script > library(engsoccerdata)
+ Make the data "engsoccerdata" avaiable for use
## Access the data
1. ?england: Overview the content of the data "engsoccerdata"
2. head(england): Gives 1st 6 rows + of the data frame.
3. tail(england): Gives bottom 6 rows + of the data frame. 
4. < Script > dat = england
5. england = england : Craete an object named England(the left england), and assign that object to a data already existed: England(the right engalnd).
## Subsetting
Ways of subsetting: 
1. By ID (Which row/column in terms of number.)
2. By name (The name of row/column)
+ england = showing the entire data set. 
+ england[ "row name" ,"column name"]
+ england[ , ] : everything
+ england[row, ] : some rows and all columns for those rows.
+ england[ 1:5, ] : the first five rows plus their corresponding columns.
4. By logical (the most important way)
+ england[ , c(FALSE,FALSE,TRUE,FALSE)] : Only give me the TRUE column (the third one)
+ england[,"result"] == "D" : Give me all the rows for the column "result". Present TRUE for the rows having a result of Draw. Otherwise, FALSE.
+ england[ england[,"result"] == "D" , ] : Just the rows of the england dataset where the result is a Draw. 
+ england[ england[,"result"] == "D" , "result" ] : Get a bunch of Ds.
### What is Everton's average score at home and average score away?
1. Finding games where Everton is the home team. 
2. Finding the score column everytime Everton is the home team. 
3. Taking the average of that vector. 
+ england[,"home"] == "Everton"
+ england[ england[,"home"] == "Everton" , "hgoal" ]
+ mean(england[ england[,"home"] == "Everton" , "hgoal" ])
+ mean(england[england[,"visitor"] == "Everton" , "vgoal"])
### How many games played after 1900 had more than 10 total goal? 
1. Games after 1900
2. Games totals > 10
+ england[,"season"] > 1900
+ sum(england[,"Season"] > 1900)
+ sum(england[,"totgoal"] > 10)
+ sum(england[,"Season"] > 1900 & england[,"totgoal"] > 10)
### First Plotting
1. plot(x=1:10,y=5:14)
2. plot(x = england[,"Season"], y = england[,"totgoal"])
3. *barplot(dat$totgoal)*
### Extra Notes
1. mean(1,2,3) = 1 ; mean(c(1,2,3)) = 2
2. A list is TRUE if all the values are TRUE. A list is FALSE if all are TRUE but one is FALSE
3. 
