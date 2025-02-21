```bash
vi 04_user_input.sh
```  
inside script  
```bash
#!/bin/bash

echo "Enter first number:"
read num1

echo "Enter second number: "
read num2

sum=$((num1 + num2))

echo "The sum is: $sum"
```  
`read` keyword is used to take userinput in commandline & insert it into variable name next to it  
save & run the script  
```bash
bash 04_user_input.sh
```  
#### Output:  
```vbnet
Enter first number:
10
Enter second number:
15
The sum is: 25
```  