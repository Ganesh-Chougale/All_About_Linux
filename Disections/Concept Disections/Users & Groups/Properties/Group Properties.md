```bash
grep "root" /etc/group
```  
#### Output:  
```console
root:x:0:
```  
## In Linux, each group has **4 key properties** stored in the `/etc/group` file. Each line in this file represents a group and follows this format:

```
group_name:password_placeholder:GID:user_list
```

---

### **Explanation of the 4 Group Properties**
1. **Group Name** (`group_name`)  
   - The name of the group.  
   - Example: `developers`, `sudo`, `admin`.

2. **Password Placeholder** (`x`)  
   - Historically, this field stored an encrypted group password.  
   - Now, it is replaced with `x`, meaning the actual password (if any) is stored in `/etc/gshadow`.  
   - Group passwords are rarely used.

3. **Group ID (GID)** (`GID`)  
   - A unique numerical identifier assigned to the group.  
   - **System groups (root, daemons, etc.)** usually have GIDs **0–999**.  
   - **Regular groups** start from GID **1000+**.  
   - Example: `1001` (group ID associated with a user group).

4. **User List** (`user_list`)  
   - A comma-separated list of users who are members of this group.  
   - The primary group of a user (defined in `/etc/passwd`) is not listed here.  
   - Example: `john,mike,sara` (users belonging to this group).

---

### **Example Entry in `/etc/group`**
```
developers:x:1001:john,mike,sara
```
- Group Name: `developers`
- Password stored in `/etc/gshadow`
- GID: `1001`
- Users in this group: `john`, `mike`, `sara`

---

### **Related Files**
1. **`/etc/gshadow`** → Stores secure group passwords and additional admin settings.
2. **`/etc/passwd`** → Links users to their primary group via GID.

---