### **What `ll` Does**
- It lists files and directories in **long format**, displaying detailed information like permissions, ownership, file size, and modification date.

### **Example Usage**
```bash
ll
```
is equivalent to:
```bash
ls -l
```
#### **Example Output of `ll`**
```bash
drwxr-xr-x  2 user user 4096 Feb 27 10:30 Documents
-rw-r--r--  1 user user  120 Feb 27 11:00 notes.txt
```
Where:
- `drwxr-xr-x` → File permissions
- `2` → Hard link count
- `user` → Owner
- `user` → Group
- `4096` → File size (in bytes)
- `Feb 27 10:30` → Last modified time
- `Documents` → File/directory name

### **If `ll` is Not Found**
- Some Linux distros (like Debian) **do not** have `ll` enabled by default.  
- You can manually enable it by adding an alias:
  ```bash
  alias ll='ls -l'
  ```
- To make it permanent, add the alias to `~/.bashrc` or `~/.bash_aliases`:
  ```bash
  echo "alias ll='ls -l'" >> ~/.bashrc
  source ~/.bashrc
  ```