install.packages("stringr")
library(stringr)
tweets = raod.csv("Tweets.csv" , headder = F)
colnames(tweets) = c("V1", "V2", "date", "topic", "handle", "text")
text = tweets$text
text = tweets %>% pull(text) 

str_detect() #tells us if a string contains a substring

str_detect(string = text[1:5], 
           pattern = "@")

str_detect(string = c(text[1:5],"I am @ home"),
           pattern = "@[[:alpha:]]")
# look for these 6 string, find one that has a @ sign

str_detect(string = c(text[1:5],"I am @ home"),
           pattern = "^@") # the thing to the right has to be the first character 

str_detect(string = c(text[1:5],"I am @ home"),
           pattern = "@$") # I want them to be the last character

str_detect(tweets$text[1:5], "[Kk]indle2") #Get both upper and lower case K

str_detect(c(tweets$text[1:5], "I love my Kindle"
             "[Kk]indle ")

str_detect(c(tweets$text[1:5], "I love my Kindle"
             "[Kk]indle$")
           
str_detect(c(tweets$text[1:5], "I love my Kindle"
              "My kindle "
              "[Kk]indle ?$") # If there is a space after, match it; if not, still match it

ste_detect(string = strs,
           pattern = "\\?$") #Treat ? as a normal ? 

###########################################################################

dates = c("June 4, 1789", 
          "December 2, 1971", 
          "Oct. 1, 1949")

# To get Months

str_extract(string = dates,
            pattern = "[[:alpha:]]+") # give me a letter and keep giving me something until it is not a letter. 
                                      # alpha gives characters
str_extract(string = date,
            pattern = "[[:alpha:]]*") 

# To get Years 
str_extract(string = dates,
            pattern = "[[:digit:]]{4}$") #carefule to not have spaces

# To get Days
str_extract(string = dates,
            pattern = "[[:digit:]]") 
str_extract(string = dates,
            pattern = "[[:digit:]]{1,2}") 

tmp = str_extract(string = dates,
            pattern = "[[:digit:]]+, ")

str_remove_all(tmp, pattern = "[ ,]")

######################################################################

strs = c("aaronkaufman@nyu.edu", "not an email", 
         "@elonmusk", "123@nyu.edu)

str_detect(strs, pattern = "[[:alpha:]]@")

str_detect(strs, pattern = "\\.[[:alpha:]]{3}")

str_detect(strs, pattern = "\\.[(com)(org)(edu)]")

str_detect(strs, pattern = "[[:alnum:]]+@[[:alnum:]]+.[[:alnum:]]+" ) 


####################################################################

dollars = c("$4.00", "10k", "11.50usd")
dollars2 = str_remove_all(dollars,
                          pattern = [[:alpha:]])
                          
dollars2 = str_extract(dollars,
                      pattern = "k",
                      replacement = "000")
                      
dollars2 = str_extract(dollars2,
           pattern = "[[:digit:]]+.?[[:digit:]]+")

mean(as.interger(dollars2))

