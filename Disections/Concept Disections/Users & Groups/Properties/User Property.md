1.  
```bash
sudo grep "gorav" /etc/passwd
```  
#### Output:  
```console
gorav:x:1000:1000:,,,:/home/gorav:/bin/bash
``` 
2.   
```bash
 sudo grep "root" /etc/passwd
```  
#### Output:  
```console
root:x:0:0:root:/root:/bin/bash
```  


## In Linux, each user account has **7 key properties** stored in the `/etc/passwd` file. Each line in this file represents a user and follows this format:

```
username:x:UID:GID:comment:home_directory:shell
```

### **Explanation of the 7 User Properties**
1. **Username** (`username`)  
   - The name used to log in.  
   - Example: `gorav`, `admin`, `developer`.

2. **Password Placeholder** (`x`)  
   - Historically, this field stored the user's encrypted password.  
   - Now, it is replaced by `x`, meaning the real password is stored in `/etc/shadow`.

3. **User ID (UID)** (`UID`)  
   - A unique numerical identifier assigned to each user.  
   - **System users (root, daemons, etc.)** usually have UID **0–999**.  
   - **Regular users** start from UID **1000+**.  
   - Example: `1001` (for a regular user), `0` (for root).

4. **Group ID (GID)** (`GID`)  
   - Specifies the user's primary group, linked to `/etc/group`.  
   - Example: `1001` (group ID associated with the user).

5. **Comment (GECOS Field)** (`comment`)  
   - A description or full name of the user.  
   - Sometimes contains additional info like phone number or office location.  
   - Example: `"gorav, Room 101, Ext 1234"`.

6. **Home Directory** (`home_directory`)  
   - The user's default directory after login.  
   - Example: `/home/gorav` (for a normal user), `/root` (for root).

7. **Login Shell** (`shell`)  
   - The default shell assigned to the user.  
   - Determines the command-line environment when logging in.  
   - Common shells:
     - `/bin/bash` (Bash shell)
     - `/bin/zsh` (Zsh shell)
     - `/bin/sh` (Basic shell)
     - `/sbin/nologin` (Prevents user login)

### **Example Entry in `/etc/passwd`**
```
gorav:x:1001:1001:gorav bro:/home/gorav:/bin/bash
```
- Username: `gorav`
- Password stored in `/etc/shadow`
- UID: `1001`
- GID: `1001`
- Comment: `gorav bro`
- Home Directory: `/home/gorav`
- Shell: `/bin/bash`

by default the comment will be empty, we can pass the comment  
1. check the user  
```bash
grep gorav /etc/passwd
```  
#### Output:  
```console
gorav:x:1000:1000:,,,:/home/gorav:/bin/bash
```  
2. give comment to user   
```bash
# use sudo it user is not root
usermod -c "gorav for RHCE" gorav
```  
```bash
grep gorav /etc/passwd
```  
#### Output:  
```console
gorav:x:1000:1000:gorav for RHCE:/home/gorav:/bin/bash
```  
we can see our comment here  