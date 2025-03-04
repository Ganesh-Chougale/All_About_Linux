## **Debian (Ubuntu, Debian)**
### **1. Create a Group**
```bash
sudo addgroup group_name
```
Example:
```bash
sudo addgroup developers
```

### **2. Create a Group with a Specific GID**
```bash
sudo addgroup --gid <GID> group_name
```
Example:
```bash
sudo addgroup --gid 2000 devops
```

### **3. Verify Group Creation**
```bash
getent group group_name
```
or
```bash
grep "group_name" /etc/group
```

### **4. Remove a Group**
```bash
sudo delgroup group_name
```
Example:
```bash
sudo delgroup developers
```