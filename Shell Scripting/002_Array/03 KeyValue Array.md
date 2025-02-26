```bash
vi 03_KV_array.sh
```  
inside it  
```bash
#!/bin/bash
declare -A myArr
myArr=( [name]=Gorav [age]=27 )
echo "${myArr[name]}"
```  
save & run  
```bash
bash 03_KV_array.sh
```  
#### Output:  
```vbnet
Gorav
```  