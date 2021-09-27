# Class 8 Part 1

## Fibonacci sequence:
1,2 (1+2=3) (2+3=5) (3+5=8) ...
1,2,3,5,8,13,21,34,55,89
Find the sum of even-value terms within 4 million.

### 1. Generate a Fibonacci sequence

Method 1: 
```
fib = c(1,2)
fib[length(fib)+1]= sum(fib[c(length(fib)-1,length(fib))])
```
+ The third term = second to last value term + the last value term.
+ The more lines I run, the longer the sequnce.

Method 2: 
```
fib = c(1,2)
for(i in 3:100) {
  fib[i] = fib[i-1] + fib[i-2]
}
```

### 2. Only selecting the ones below 4M.
First method:
```
fib = fib[fib < 4000000 ]
fib
```
OR: 
```
fib = c(1,2)
for(i in 3:100) {
  if (fib[i-1] + fib[i-2] < 4000000) {
    fib[i] = fib[i-1] + fib[i-2]
  }
}
```
Second method:
```
fib = c(1,2)
i = 2
while(fib[i] < 4000000) {
  fib[i+1] = fib[i] + fib[i-1]
}
```
Replace i with "length(fib)" : 
```
fib = c(1,2)
while(fib[length(fib)] < 4000000) {
  fib[length(fib)] = fib[length(fib)] + fib[length(fib)-1]
}

```
### 3 Take the even ones & Sum them all
```
fib_even = sum(fib[fib%% 2 == 0]])
```
