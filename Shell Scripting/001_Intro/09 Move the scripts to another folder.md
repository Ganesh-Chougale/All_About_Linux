for next we will learning `Array` so i decide to have dedicated folders to each sections. for thing we have done yet lets keep those script in `01_Into` folder.
```bash
ls
```  
#### Output:  
```bash
01_basic.sh  02_comments.sh  03_var_demo.sh  04_user_input.sh  05_dyn_vars.sh  06_const_var.sh
```  
### create a folder `01_Into`  
```bash
mkdir -p 01_Intro 
```  
mkdir → make directory.
-p → Prevents errors if the folder already exists.
```bash
ls
```  
#### Output:  
```bash
01_Intro  01_basic.sh  02_comments.sh  03_var_demo.sh  04_user_input.sh  05_dyn_vars.sh  06_const_var.sh
```  

### move all scripts from current directory to `01_Intro`  
```bash
mv *.sh 01_Intro/
```  
```bash
ls
```  
#### Output:  
```vbnet
01_Intro
```  
```bash
cd 01_Intro/
ls
```  
#### Output:  
```bash
01_basic.sh  02_comments.sh  03_var_demo.sh  04_user_input.sh  05_dyn_vars.sh  06_const_var.sh
```  