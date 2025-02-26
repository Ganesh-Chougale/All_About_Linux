```bash
mkdir 03_String
cd 03_String/
```  
```bash
vi 01_str_ops.sh
```  
inside it  
```bash
#!/bin/bash
myStr="Hey bro, How are you?"
echo "String : $myStr"

strLen=${#myStr}
echo "The length of string is: $strLen"

upperCased=${myStr^^}
lowerCased=${myStr,,}
echo "UpperCased ---- $upperCased"
echo "LowerCased ---- $lowerCased"

bro_to_sis=${myStr/bro/sis}
echo "String : $bro_to_sis"

sliced=${myStr:9:3}
echo "3 character from 9th index : $sliced"
```  
save & run  
```bash
bash 01_str_ops.sh
```  
#### Output:  
```shell
String : Hey bro, How are you?
The length of string is: 21
UpperCased ---- HEY BRO, HOW ARE YOU?
LowerCased ---- hey bro, how are you?
String : Hey sis, How are you?
3 character from 9th index : How
```  