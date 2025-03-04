### **Mutual Commands for User Modification (Same in Red Hat & Debian)**  
These commands work **identically** on both **Red Hat-based** (RHEL, CentOS, Fedora) and **Debian-based** (Ubuntu, Debian) systems.  

| Action | Command |
|--------|---------|
| **Rename a user** | `sudo usermod -l new_username old_username` |
| **Change UID** | `sudo usermod -u new_UID username` |
| **Change primary group** | `sudo usermod -g new_group username` |
| **Add user to a supplementary group** | `sudo usermod -aG group_name username` |
| **Lock a user account** | `sudo usermod -L username` |
| **Unlock a user account** | `sudo usermod -U username` |
| **Change home directory** | `sudo usermod -d /new/home/path -m username` |
| **Change shell** | `sudo usermod -s /bin/bash username` |
| **Expire user account** | `sudo usermod -e YYYY-MM-DD username` |
| **Force user to change password on next login** | `sudo passwd -e username` |

---

### **Different Commands Based on Distros**
#### **1. Create a New User**
| Action | Red Hat (RHEL, CentOS, Fedora) | Debian (Ubuntu, Debian) |
|--------|-------------------------------|--------------------------|
| Create a user **without home directory** | `sudo useradd username` | `sudo useradd username` |
| Create a user **with a home directory** | `sudo useradd -m username` | `sudo adduser username` (interactive) |

💡 **Note:**  
- In **Debian**, `adduser` is an **interactive** script that prompts for details (password, full name, etc.).  
- In **Red Hat**, `useradd` requires `-m` to create a home directory.  

---

#### **2. Delete a User**
| Action | Red Hat | Debian |
|--------|--------|--------|
| Delete user **(keep home directory)** | `sudo userdel username` | `sudo deluser username` |
| Delete user **(remove home directory)** | `sudo userdel -r username` | `sudo deluser --remove-home username` |

---

#### **3. Modify Group Membership**
| Action | Red Hat | Debian |
|--------|--------|--------|
| Add a user to a group | `sudo usermod -aG group_name username` | `sudo usermod -aG group_name username` |
| Remove a user from a group | `sudo gpasswd -d username group_name` | `sudo deluser username group_name` |

💡 **Alternative in Debian:**  
```bash
sudo deluser username group_name
```
---

#### **4. List User Information**
| Action | Red Hat | Debian |
|--------|--------|--------|
| Show user details | `id username` | `id username` |
| Show all users | `cat /etc/passwd` | `cat /etc/passwd` |
| Show groups of a user | `groups username` | `groups username` |

---

#### **5. Set Password Aging Policies**
| Action | Red Hat | Debian |
|--------|--------|--------|
| View password aging info | `sudo chage -l username` | `sudo chage -l username` |
| Set password expiration (in days) | `sudo chage -M 90 username` | `sudo chage -M 90 username` |

---

### **Key Takeaways**
1. **Mutual commands:** Most `usermod`, `passwd`, `chage`, and `groupmod` commands are the same.
2. **Debian uses `adduser/deluser`**, while **Red Hat uses `useradd/userdel`**.
3. **Red Hat does NOT create a home directory by default**, while **Debian does** when using `adduser`.
4. **Different user removal commands** (`deluser` in Debian, `userdel` in Red Hat).
5. **Group modifications (`deluser username group_name`) exist only in Debian.**

---