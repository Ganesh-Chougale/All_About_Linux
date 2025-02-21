```bash
vi 02_comments.sh
```  
inside it  
```vi
#!/bin/bash
echo "Checking Comments"

# this is a single line comment

<<comment
this
is
a
multiline
comment
```  
if we run the script  
```bash
bash 02_comments.sh
```  
#### Output:  
```vbnet
Checking Comments
```  
it works & commented part is skipped by interpreter  