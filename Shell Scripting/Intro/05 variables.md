```bash
vi 03_var_demo.sh
```  
inside file
```vi
#!/bin/bash

firstName="Ganesh"
lastName="Chougale"
age=26

echo "My name is $firstName $lastName & my age is $age"
```  
`space between variableName, = & value will cause error.`  
then save  
now run  
```bash
bash 03_var_demo.sh
```  
#### Output:  
```vbnet
My name is Ganesh Chougale & my age is 26
```  