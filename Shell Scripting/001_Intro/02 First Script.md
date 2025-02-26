## 1. Create seperate folder only for scripts  
#### create folder:  
```bash
mkdir my_scripts
```   
```bash
ls
```  
#### Output:  
```vbnet
Desktop    Music     Templates   thinclient_drives
Documents  Pictures  Videos
Downloads  Public    my_scripts
```  
#### Terminal:  
```bash
cd my_scripts/
pwd
```  
#### Output:  
```vbnet
/home/gorav/my_scripts
```  

## 2.  create your first script  
```bash
vi 01_basic.sh
```  
it will create & open `01_basic.sh` file using `vi` text editor.  
press `i` to get in insert mode.  
```vi
#!/bin/bash

echo "Hi Buddy!"
```  
press `Esc` to get out from insert mode.  
press `Shift` + `:` & type `wq` & then hit `Enter`  
it will save the script  

### 3. lets Read & Disect the script  
```bash
cat 01_basic.sh
```  
#### Output:  
```vbnet
#!/bin/bash
echo "Hi Buddy!"
```  
**lets Disect the syntax**:   
- `#!` also known as shabang  
(#: hash, !: bang that why #!: shebang)  
- `/bin/bash` means we are telling to user bash interpreter from /bin folder.
althought it is not neccesary to write first line but it is good practice to follow this, it reduces conflicts just in case if any other machine uses other shell other than bash.  
- `echo` is the printing statement for terminal & it prints the output which is thing next to it, in our case it is a string `"Hi Buddy!"`.  

### 4. Before running script  
before running any script we need to be sure that  
script has execute permission `rwx` (Read, Write, Execute)  
```bash
ls -ltr
# l : list all files in long formatt =  permissions, file_index, user_name, file_size, date, time, file_name
# t : Sort by modification time (newest last)
# r : Reverse order (oldest first)
```  
Permission format is `user`, `group` & at last `other`  
#### Output:  
```vbnet
-rw-rw-r-- 1 gorav gorav 29 Feb 21 18:49 01_basic.sh
```  
##### Breakdown:  
- `-rw-rw-r--` → File permissions  
  - `-` → Regular file  
  - `rw-` → User (`gorav`) can read & write  
  - `rw-` → Group (`gorav`) can read & write  
  - `r--` → Others can only read  
- `1` → Hard link count  
- `gorav gorav` → Owner and group  
- `29` → File size (bytes)  
- `Feb 21 18:49` → Last modified date & time  
- `01_basic.sh` → File name  

### 5. run the script  
there are 3 ways we can run our script  
#### 1st: need of execution permission  
```bash
./script_name.sh
```  
#### 2nd: need of execution permission  
```bash
/full_path/script_name.sh
```  
#### 3rd: no need of execution permission or skip the permission    
```bash
bash script_name.sh
```  
now lets try in our scenario  
```bash
ls
```  
#### Output:  
```vbnet
01_basic.sh
```  
#### 1st: need of execution permission  
```bash
./01_basic.sh
```  
#### Output:  
```vbnet
-bash: ./01_basic.sh: Permission denied
```  
#### 2nd: need of execution permission  
```bash
/home/gorav/my_scripts/01_basic.sh
```  
#### Output:  
```vbnet
-bash: /home/gorav/my_scripts/01_basic.sh: Permission denied
```  
#### 3rd: no need of execution permission or skip the permission    
```bash
bash 01_basic.sh
``` 
#### Output:  
```vbnet
Hi Buddy!
```  

### 6. change the permission  
```bash
chmod +x 01_basic.sh
# +x : gives eXecution permission 
```  
```bash
./01_basic.sh
# OR
/home/gorav/my_scripts/01_basic.sh
```  
#### Output:  
```vbnet
Hi Buddy!
```  
```bash
l -ltr
```  
#### Output:  
```vbnet
-rwxrwxr-x 1 gorav gorav 29 Feb 21 18:49 01_basic.sh*
```  
& it will change the color of file too to indicate the change  


`Ctrl + C` → Terminates (kills) the running process.  
`Ctrl + Z `→ Stops (pauses) the process and puts it in the background.  