In Linux, users are categorized into different types based on their roles and permissions. The main types of users are:

1. **Root User (Superuser)**  
   - Has complete control over the system.  
   - Can execute any command, modify any file, install/remove software, and manage other users.  
   - Identified by `UID 0`.  

2. **Regular User (Normal User)**  
   - Created by the root user.  
   - Has a unique home directory (e.g., `/home/username`).  
   - Can execute commands, run applications, and manage personal files.  
   - Cannot modify system files or manage other users without `sudo` access.  

3. **System Users (Service Accounts)**  
   - Created by the system or during software installation.  
   - Used for running system services (e.g., `mysql`, `apache`, `nobody`).  
   - Typically do not have login access.  

4. **Guest User**  
   - Temporary user with limited permissions.  
   - Typically used for one-time access with no permanent home directory.  

5. **Sudo User**  
   - A regular user with elevated privileges.  
   - Can execute administrative commands using `sudo`.  
   - Managed via the `/etc/sudoers` file.  

6. **Network Users (LDAP/NIS Users)**  
   - Stored in a centralized authentication system.  
   - Used in enterprise environments where users log in from different machines.  

To check the user type or switch users, you can use the following commands:  
- ### A. `whoami` – Displays the current user.  
```bash
whoami
```  
#### Output:  
```vbnet
rserver
```  
- ### B. `id` – Shows user and group IDs.  
```bash
id
```  
#### Output:  
```vbnet
uid=1000(rserver) gid=1000(rserver) groups=1000(rserver),10(wheel) context=unconfined_u:unconfined_r:unconfined_t:s0-s0:c0.c1023
```  
- ### C. `sudo -i` – Switch to root.  
#### if your CLI hostname ends with `$` sign, this means you are logged as a normal user  
```vbnet
username-@HostMachine: $
```  
```bash
sudo -i
# change it to superuser
```  
#### after switching user to root, CLI hostname will appear with `#` sign, this means now you are logged as a root/normal user  
#### Output:  
```vbnet
root-@HostMachine: #
```  
- ### D. `su username` – Switch to another user.  
```bash
su username
# to switch to other user
```  

to see all user  
```bash
cat /ect/passwd
```  