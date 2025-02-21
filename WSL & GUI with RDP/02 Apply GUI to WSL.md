###  1. Open WSL & update the enviroment  
open WSL command line  
#### Terminal:  
```bash
sudo apt update
# Fetches the latest package lists from the repositories.
# Doesn't install anything, just checks for updates.
```  
#### Terminal:  
```bash
sudo apt upgrade -y
# Installs the latest versions of packages.
# The -y flag automatically confirms all prompts.
```  

### 2. install TaskSel  
`tasksel` is a tool for installing groups of related packages (like a full desktop environment).  
#### Terminal:  
```bash
sudo apt install tasksel -y
```  

### 3. Open TaskSel  
#### Terminal:  
```bash
sudo tasksel
```  
use `Down-Arrow` keys to navigate & `Space` to check selection.
select:
`Debian Desktop Enviroment` & `KDE Plasma`  
`Tab` to navigate to ok & `Enter`  
- this process can take an hour or less depending on internet & machine  

### 4. Install XRDP  
`xrdp` is an open-source Remote Desktop Protocol (RDP) server that lets you connect to your WSL (Ubuntu/Debian) via Windows Remote Desktop (RDP).
#### Terminal:  
```bash
sudo apt install xrdp -y
```  