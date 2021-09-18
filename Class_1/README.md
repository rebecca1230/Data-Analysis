# Class 1 Part 1
## R Working Blocks
1. <UP-LEFT> Scripte : Record and save what we type. 
2. <BOTTOM-LEFT> Console/Terminal : Where we tell the computer to do stuff.
3. <UP-RIGHT> Environment : Save stuff we want to use later. 
4. <BOTTOM-RIGHT> Create graphs.
## Primitives
1. (#) Comment
2. (asterisk) multiplication 
4. (/) division
5. (+) addition
6. sum(1,1) addition 
## Syntax 
1. sum(1,2) : (a) "sum" is a function (b) 1 and 2 are the arguments (c) , separates arguments
2. prod(2,3,2) = 12 
## Functions 
1. %% : Modulo function generates remainder. EX: 5 %% 2 = 1 
2. c() : concatenate/combine function generates the same amount of things we provided to it. EX: c(1,2,3)
3. rep(what we want to repeat, times of repetition) : Repeat function. EX: rep(10,2) = 10 10 ; rep(10,3) = 10 10 10 
4. seq(first value, last value) : Sequence function gives all the numbers between the firsst and last value. EX: seq(2,5) = 2 3 4 5 
   seq(2,5) = 2:5 = seq(2,5,by=1)
6. seq(2,5,by=0.5) = 2, 2.5, 3, 3.5, 4, 4.5, 5
7. ?seq : asking the bottom-right block what this function is.
   seq(from = 2, to = 11, by = 0.25
### How to generate 111222333444
1. c(1,1,1,1,2,2,2,2,3,3,3,3,4,4,4,4)
2. c(rep(1,3), rep(2,3), rep(3,3), rep(4,3)) 
3. rep(x=seq(1,4), each=4)
4. rep(1:4 , each=4)
5. c(rep(1:4, each=4))
>> c(rep(1:4, each=4), rep(1:4, each=4)) = 11112222333344441111222233334444
### How to generate 1234234534564567
1. c(1:4,2:5,3:6,4:7)
2. rep(1:4,each=4 + rep(0:3))
3. rep(1:4,4) + rep(rep(0:3),4)
``` 

```
