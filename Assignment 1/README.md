dates <- c("02/27/92", "02/27/92", "01/14/92", "02/28/92", "02/01/92")
as.Date(dates, "%m/%d/%y")

mdat = matrix(c(1,2,3, 11,12,13), nrow = 2, ncol = 3, byrow = TRUE,
              dimnames = list(c("row1", "row2"),
                              c("C.1", "C.2", "C.3")))
mdat
#########################################################
mdat = matrix(c(TRUE, "UK", 169, 87, "12/30/99",
                FALSE, "Switzerland", 180, 80, "01/28/00",
                TRUE, "Japan", 200, 90, "11/04/99",
                TRUE, "China", 167, 77, "09/23/98",
                TRUE, "Singapore", 160, 93, "07/16/98",
                FALSE, "India", 166, 88, "01/31/01",
                FALSE, "Italy", 174, 76, "04/04/99",
                TRUE, "Jordon", 158, 89, "03/15/98",
                TRUE,"Germany", 182, 95, "11/21/00",
                TRUE,"Greece", 190, 91,  "10/10/97"
), 
nrow = 10, 
ncol = 5, 
byrow = TRUE,
dimnames = list(c("Elizabeth", "Bob", "Michael", "Rebecca", "Chloe", "Scarlett", "Jackson", "Emma", "Lancelot", "Anderson"  
),
c("Attendance", "Nationality", "Height", "Grade", "Birth")))
mdat
row.names(mdat)
##################################################
setwd("D:/Dropbox/Data Analysis F21/homework/hw1")
load('registeredvoters.Rdata')
head(ps)

# 1. What is the mean of the registered voters variable?
mean(ps[,"rv"])
# ANSWER: 1362.493

# 2. What is the variance of the registered voters variable?
x = ps[, "rv" ]
var(x, y = NULL, na.rm = TRUE)
# ANSWER: 1886490

# 3-1. Set row names of the dataset to be equal to the polling station id variable. 
# 3-2. Use row name indexing to report the name of the polling station with psid 089/081.
rownames(ps) = ps [ , "psid"]
print("Modified DataFrame :")
print(ps)
ps [ "089/081"  , "psname"]

# 4-1.How many different constituencies are contained in the data? 
# 4-2. How many polling stations from each constituency are contained in the data? (Hint: unique())
y = ps[,"const"]
unique(y)

a = ps[ps[,"const"] == "LANGATA","psname"]
unique(a)

b = ps[ps[,"const"] == "KINANGOP","psname"]
unique(b)

# ANSWER: (1) 2 Constituencies (2) For "LANGATA", 34 stations. For "KINANGOP", 100 stations. 

# 5-1. How many polling stations have zero registered voters? 
# 5-2. What is the name of the polling station that has 661 registered voters?

ps[,"rv"] == 0
ps[ ps[,"rv"] == 0 , "rv" ]
# ANSWER: 4 polling stations. 

ps[ , "rv"] == 661
ps[ ps[ , "rv"] == 661 , "psname"]
# ANSWER: "KIMURI SECONDARY SCHOOL."

# 6-1. Report the mean of the registered voters for the polling stations in Langata constituency; do the same for Kinangop constituency. 
# 6-2. Which constituency has a higher average number of registered voters?

ps[, "const" ] == "LANGATA"
mean(ps[ ps[, "const" ] == "LANGATA" , "rv" ])
mean(ps[ ps[, "const" ] == "KINANGOP" , "rv" ])
# ANSWER: (1) "LANGATA" 2844.059 (2) "KINANGOP" 858.76 (3) "LANGATA" has a higher average number of registered voters

# Calculate the standard error for the mean of the registered voter variable for Langata and Kinangop.
# Which has the lower standard error? Describe why the standard error is lower in terms of variance and sample size.
