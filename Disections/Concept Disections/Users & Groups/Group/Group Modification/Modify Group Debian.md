## **Debian (Ubuntu, Debian)**
### **1. Rename a Group**
```bash
sudo groupmod -n new_group_name old_group_name
```
Example:
```bash
sudo groupmod -n hbull hstud
```

### **2. Change Group ID (GID)**
```bash
sudo groupmod -g new_GID group_name
```
Example:
```bash
sudo groupmod -g 3000 hstud
```

### **3. Change a Group’s Password** (Stored in `/etc/gshadow`)
```bash
sudo gpasswd group_name
```
Example:
```bash
sudo gpasswd developers
```