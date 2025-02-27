To enable **clipboard sharing** between Windows (host) and Red Hat OS (guest) in **Oracle VirtualBox**, follow these steps:  

### **1. Enable Clipboard Sharing in VirtualBox Settings**  
1. **Power off** your Red Hat VM (if running).  
2. Open **VirtualBox Manager**.  
3. Select your **Red Hat VM** → Click **Settings**.  
4. Go to **General** → **Advanced** tab.  
5. Set **Shared Clipboard** to **Bidirectional** (for both copy-paste).  
6. Click **OK** and start your VM.  

### **2. Access the guest Disk**  
on running VM instance click on  
`Menu Bar`----->`Devices`----->`Insert guest additions CD image`  
this will activate VBox 

### 3. run the VBox:  
search VBox in desktop or application, it will open the directory of VBox.  
open the directory in terminal & run the autorun script    
```bash
sudo ./autorun.sh
```  
or 
```bash
sudo ./VBoxLinuxAdditions.run
```  

### 4. Restart VM & instance  