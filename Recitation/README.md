# 0912 Recitation

## Loop over a Matrix: "Let's Loop" 

...

ttt <- matrix(c("O", NA, "X", NA, "O", NA, "X", "O", "X"), nrow = 3, ncol = 3)
ttt

? paste()
paste (..., sep = " ", collapse = NULL, recycle0 = FALSE)

for (row in 1:nrow(ttt)) {
  for (column in 1:ncol(ttt)) {
    print(paste("On row", row,  "and column", column, "the board contains", ttt[row, column] ) )
  }
}

...

## Loop over a Matrix: Combine both Loop and Ifs

Students = c("Aida", "Bruce", "Cecilia", "Daniel")
Majors = c("PoliSci", "Biology", "Econ", "SocPol")

for ( x in 1:length(Students) ) { 
  if ( Majors[x] == "PoliSci" ) {
    print (paste(Students[x], "studies Political Science"))
  } else if (Majors[x] == "Econ") {
    print (paste(Students[x], "studes Economics"))
  } else if (Majors[x] == "SocPol") {
    print (paste(Students[x], "studies Social Policy"))
  } else {
    print (paste(Students[x], "studeis Unkown Major"))
  }
}

## Functions: Create a Celsius to Fahrenheit Converter

convertCF = function(x, y) {
  return((x*1.8) + 32)
} 

convertCF(20)

## Functions: More on Your Converter

TempinAD = c(32,32,30,31.5,29,30,35)

convertCF (TempinAD)

for ( a in (TempinAD) ) {
  print(convertCF(a))
}

