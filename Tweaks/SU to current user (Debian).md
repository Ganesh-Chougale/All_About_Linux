
# **`Debian`**:  
## 1. check the current username  
```bash
whoami
```  
it will give you your current name  
## 2. Enter into super user & grant current user sudo previllages  
change current to root user  
```bash
sudo -i
# then password
```  
for `Debian destros`  
```bash
usermod -aG sudo <currentUserName>
```  
change root to current user  
```bash
exit
# exit from root user or
su - <currentUserName>
# change user by your username
```  
check the group  
```bash
groups ${whoami}
```  
it will show `currentUserName sudo`   

## 3. Verify  
```bash
whoami
```  
output suppose to be `currentUserName`  
but after  
```bash
sudo whoami
# then password
```  
output suppose to be `root`  