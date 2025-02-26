```bash
mkdir 05_Arithmatics
cd 05_Arithmatics
```  
```bash
vi 01_arithmatic.sh
```  
inside it  
```bash
#!/bin/bash

x=10
y=5

let add=$x+$y
echo "addition of $x & $y is: $add"

let sub=$x-$y
echo "subtraction of $x & $y is: $(($x-$y))"

let mult=$x*$y
echo "multiplication of $x & $y is: $mult"

let div=$x/$y
echo "division of $x & $y is: $div"
```  