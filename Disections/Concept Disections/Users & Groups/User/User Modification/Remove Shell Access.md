### if we want to remove the shell access from a certain user  
1. Check the user's current shell  
```bash
grep username /etc/passwd
```  
ex.  
```bash
grep user01 /etc/passwd
```  
#### Output:  
```console
user01:x:1002:1002:,,,:/home/user01:/bin/bash
```  

2. remove the shell access  
```bash
usermod -s /sbin/nologin username
```  
ex.  
```bash
# sudo this if not root user
usermod -s /sbin/nologin user01
```  

3. Verify the proceess  
```bash
grep username /etc/passwd
```  
ex.  
```bash
grep user01 /etc/passwd
```  
#### Output:  
```console
user01:x:1002:1002:,,,:/home/user01:/sbin/nologin
```   