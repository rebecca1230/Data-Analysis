# Class 1 Part 1
## R Working Blocks
1. < UP-LEFT > Scripte : Record and save what we type. 
2. < BOTTOM-LEFT > Console/Terminal : Where we tell the computer to do stuff.
3. < UP-RIGHT > Environment : Save stuff we want to use later. 
4. < BOTTOM-RIGHT > Create graphs.
## Primitives
1. (#) Comment
2. (asterisk) multiplication 
3. (/) division
4. (+) addition
5. sum(1,1) addition 
## Syntax 
1. sum(1,2) : (a) "sum" is a function (b) 1 and 2 are the arguments (c) , separates arguments
2. prod(2,3,2) = 12 
## Functions 
1. %% : Modulo function generates remainder. EX: 5 %% 2 = 1 
2. c() : concatenate/combine function generates the same amount of things we provided to it. EX: c(1,2,3)
3. rep(what we want to repeat, times of repetition) : Repeat function. The default repetition is 1. EX: rep(10,2) = 10 10 ; rep(10,3) = 10 10 10 
4. seq(first value, last value) : Sequence function gives all the numbers between the firsst and last value. EX: seq(2,5) / 2:5 / seq(2,5,by=1) = 2 3 4 5
5. seq(2, 5, by=0.5) = 2, 2.5, 3, 3.5, 4, 4.5, 5
6. ?seq : asking the bottom-right block what this function is.
### How to generate 111222333444
1. c(1,1,1,1,2,2,2,2,3,3,3,3,4,4,4,4)
2. c(rep(1,3), rep(2,3), rep(3,3), rep(4,3)) 
3. rep(x=seq(1,4), each=4)
4. rep(1:4 , each=4)
5. c(rep(1:4, each=4))
6. c(rep(1:4, each=4), rep(1:4, each=4)) = 11112222333344441111222233334444
### How to generate 1234234534564567
1. c(1:4,2:5,3:6,4:7)
2. rep(1:4,each=4) + rep(0:3) means (1111222233334444 + 0123) 
+ 1111222233334444 + 0123012301230123 = up + bottom = 1234234534564567
## Objects: Create values 
### One object
1. <Script> name = "Aaron" 
2. Highlight and "Run"
3. <Environment> Appears name means the value "Aaron"
### Two objects
1. <Script> names = c("aaron","omer")  
<< A vector/objects with 2 objects inside it. 
2. Highlight and "Run"
3. <Environment> Appears: chr [1:2] "aaron" "omer" 
<< chr means character object 
   int means interger object
### Integer and character 
1 + 1 = 2
"1" + "1" = Error
### Matrix 
our.matrix = matrix(data = 1:25, nrow=5, ncol=5, byrow=TRUE)
<<< Left to right; 5 rows. 
our.matrix = matrix(data = 1:25, nrow=5, ncol=5, byrow=FALSE)
<<< Up to down; 5 columns. 
class(our.matrix) = "matrix" 

our.matrix = as.data.frame(our.matrix)

<<< The columns have names.

class(our.matrix) = "data.frame"
