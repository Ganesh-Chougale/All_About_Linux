# `Scenario` : we downlaoded videos in WSL & want to copy them in windows  
### **Method 1: Access WSL Files from Windows Explorer**  
1. Open **File Explorer** in Windows.  
2. In the address bar, type:  
   ```
   \\wsl$
   ```
3. Press **Enter**.  
4. Navigate to your Linux home directory (`Ubuntu → home → your_username`).  


### **Method 2: Move Files to Windows Path Directly**  
If you want to **save the files in Windows while downloading**, use:  
```sh
mv /path/to/videos /mnt/c/Users/YourWindowsUsername/Videos/
```
or directly download them to Windows:  
```sh
gdown --folder https://drive.google.com/drive/folders/FOLDER_ID -O /mnt/c/Users/YourWindowsUsername/Videos/
```

---

### **Method 3: Use WSL Terminal in Windows Explorer**  
1. Open the folder where you want the files in **Windows Explorer**.  
2. Type `wsl` in the address bar and press **Enter**.  
3. Now you are inside that folder in WSL, and you can move files easily:  
   ```sh
   mv ~/Downloads/*.mp4 .
   ```