```bash
mkdir 04_User_Input
cd 04_User_Input
```  
```bash
vi 01_user_input.sh
```  
inside it  
```vim
#!/bin/bash

# Normal method
echo "what is your name: "
read name
echo "your name is: $name"

# better way
read -p "what is your nickname: " nName
echo "your nickname is: $nName"
```  
then save and run  
```bash
bash 01_user_input.sh
```  
#### Output:  
```shell
what is your name:
Ganesh
your name is: Ganesh
what is your nickname: Gorav
your nickname is: Gorav
```  