```bash
vi 02_array_append.sh
```  
inside it  
```bash
#!/bin/bash
myArr=(1 2 3)
myArr+=(4 5 6)
echo "myArr:( ${myArr[*]} )"
```  
save & run  
```bash
bash 02_array_append.sh
```  
#### Output:  
```vbnet
myArr:( 1 2 3 4 5 6 )
```  