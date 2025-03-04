## **Red Hat (RHEL, CentOS, Fedora)**
### **1. Create a Group**
```bash
sudo groupadd group_name
```
Example:
```bash
sudo groupadd developers
```

### **2. Create a Group with a Specific GID**
```bash
sudo groupadd -g GID group_name
```
Example:
```bash
sudo groupadd -g 2000 devops
```

### **3. Verify Group Creation**
```bash
getent group group_name
```
or
```bash
grep "group_name" /etc/group
```
Example:
```bash
getent group developers
```

### **4. Remove a Group**
```bash
sudo groupdel group_name
```
Example:
```bash
sudo groupdel developers
```