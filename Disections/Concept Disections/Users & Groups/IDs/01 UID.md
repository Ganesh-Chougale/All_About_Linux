### **What is a UID (User ID) in Linux?**  
A **UID (User ID)** is a unique numerical identifier assigned to each user on a Linux system. It is used by the system to identify users, control permissions, and manage file ownership.

---

### **Types of UIDs:**
1. **System UIDs (0–999)**  
   - Reserved for system users and services.  
   - Example:  
     - `root` has UID **0** (superuser).
     - System services like `nobody`, `www-data`, `daemon`, etc., typically have UIDs below 1000.

2. **Regular User UIDs (1000 and above)**  
   - Assigned to normal users when they are created.  
   - Example:
     ```bash
     id username
     ```
     Output:
     ```
     uid=1000(gorav) gid=1000(gorav) groups=1000(gorav),10(wheel)
     ```
     Here, `gorav` has UID **1000**.

3. **Special UID Ranges** (varies by distribution)  
   - Some distros may reserve **100-499** for dynamically created users.  
   - Some cloud-based Linux instances may start normal user UIDs from **500** instead of **1000**.

---

### **How to Check Your UID?**
1. Check your own UID:
   ```bash
   id -u
   ```
   #### Output:  
   ```console
   1000
   ```  
2. Check UID of a specific user:
   ```bash
   id -u username
   ```
   #### Output:  
   ```console
   1000
   ```  
3. View UID mapping from `/etc/passwd`:
   ```bash
   grep username /etc/passwd
   ```
   OR  
   ```bash
   cat /etc/passwd | grep username
   ```
   Example output:
   ```
   gorav:x:1000:1000:,,,:/home/gorav:/bin/bash
   ```
   Here, `1000` is the UID.

---

### **Changing a User's UID**
Only a root user can modify UIDs using `usermod`:
```bash
sudo usermod -u 2000 username
```
This changes `username`'s UID to **2000**.

---

### **Why is UID Important?**
- Controls **file ownership**: Each file has an **owner UID**.
- Affects **permissions**: `chmod`, `chown`, and `chgrp` use UID-based ownership.
- Determines **privileges**: `UID 0` (root) has full system access.
- **SELinux & ACLs** may use UID for security policies.