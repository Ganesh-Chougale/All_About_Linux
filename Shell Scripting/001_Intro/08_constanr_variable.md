Once you defined a variable and don’t wanna change it until end of the script.  
```bash
vi 06_const_var.sh
```  
inside it  
```bash
#!/bin/bash
readonly CITY_NAME="Gotham"
echo "Batman lives in $CITY_NAME city"
```  
give prefix syntax keyword: `readonly`  
now save & run  
```bash
bash 06_const_var.sh
```  
#### Output:  
```vbnet
Batman lives in Gotham city
```  
now lets try to change the constant variable  
```bash
#!/bin/bash
readonly CITY_NAME="Gotham"
echo "Batman lives in $CITY_NAME city"

CITY_NAME="Metro-Polis"
```  
```bash
bash 06_const_var.sh
``` 
```bash
Batman lives in Gotham city
06_const_var.sh: line 5: CITY_NAME: readonly variable
```  