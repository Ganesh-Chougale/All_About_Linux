### **What is a GID (Group ID) in Linux?**  
A **GID (Group ID)** is a unique numerical identifier assigned to a group in Linux. Groups help manage user permissions by allowing multiple users to share access to files and system resources.

---

### **Types of GIDs:**
1. **System GIDs (0–999)**
   - Reserved for system groups and services.  
   - Example:
     - `root` group has GID **0**.
     - Other system groups include `daemon`, `adm`, `www-data`, etc.

2. **Regular User GIDs (1000 and above)**
   - Assigned when a new user is created.
   - Typically, a user’s primary group has the same GID as their UID.
   - Example:
     ```bash
     id gorav
     ```
     Output:
     ```
     uid=1000(gorav) gid=1000(gorav) groups=1000(gorav),10(wheel)
     ```
     Here, `gorav` has GID **1000** (same as UID) and is also part of group **wheel** (GID 10).

3. **Special GID Ranges** (varies by distribution)  
   - Some distros may reserve **100-499** for dynamically created system groups.  
   - Cloud-based Linux instances may start normal user GIDs from **500** instead of **1000**.

---

### **How to Check Your GID?**
1. Check your own GID:
   ```bash
   id -g
   ```
   #### Output:
   ```console
   1000
   ```
2. Check GID of a specific user:
   ```bash
   id -g username
   ```
3. View all groups and their GIDs:
   ```bash
   grep username /etc/group 
   ```
   OR  
   ```bash
   cat /etc/group | grep username
   ```
   Example output:
   ```
   gorav:x:1000:
   wheel:x:10:gorav
   ```
   Here, `gorav` has a primary group with GID **1000** and is a member of the `wheel` group (GID **10**).

---

### **Changing a User's GID**
Only a root user can modify a user's primary GID using `usermod`:
```bash
sudo usermod -g 2000 username
```
This changes `username`'s primary group to GID **2000**.

To change a file’s group ownership:
```bash
sudo chown :newgroup filename
```

---

### **Why is GID Important?**
- Controls **group ownership** of files and directories.
- Helps in **permission management** by allowing multiple users to share resources.
- Used in **Access Control Lists (ACLs)** for fine-grained permissions.
- `chmod` uses **group permissions** (e.g., `chmod g+w file` gives write access to the group).