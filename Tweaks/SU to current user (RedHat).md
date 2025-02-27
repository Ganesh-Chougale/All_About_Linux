# **`RedHat`**:  
## 1. check the current username  
```bash
whoami
```  
it will give you your current name  
## 2. Enter into super user & grant current user sudo previllages  
change current to root user  
```bash
su -
# then password
```  
for `RedHat destros`  
```bash
usermod -aG wheel <currentUserName>
```  
change root to current user  
```bash
su - <currentUserName>
```  
check the group  
```bash
groups ${whoami}
```  
it will show `currentUserName wheel`   

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