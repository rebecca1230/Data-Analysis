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
1. By ID
2. By name
+ england = showing the entire data set. 
+ england[,"visitor"]
4. By logical (the most important way)

