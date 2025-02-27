### **Types of Terminals (1 to 6) in Linux**  
**`TTY`**: TeleTYpewriter  
Linux provides **six virtual consoles (TTYs)** by default, which can be accessed using **Ctrl + Alt + F1 to F6**. These are called **Virtual Terminals (VTs)** and are directly connected to the system.  

#### **📌 List of Terminals (TTY1 - TTY6)**
| **Terminal** | **Description** |
|-------------|----------------|
| **TTY1** | The first virtual console (text-based login screen). |
| **TTY2** | Second virtual console, available for another login session. |
| **TTY3** | Third virtual console, can be used to log in separately. |
| **TTY4** | Fourth virtual console, useful for multitasking. |
| **TTY5** | Fifth virtual console, often unused but available. |
| **TTY6** | Sixth virtual console, another available login shell. |

### **🔹 How to Access TTYs?**  
Press **Ctrl + Alt + F1** to **Ctrl + Alt + F6** to switch between them.  

### **🔹 How to Switch Back to GUI?**  
Press **Ctrl + Alt + F7** (or `F2` in newer systems like Ubuntu).  

### **🔹 Difference Between TTY and PTY**  
- **TTY (Virtual Terminal):** Directly connected to the system, used for login.  
- **PTY (Pseudo Terminal):** Created by terminal emulators (e.g., GNOME Terminal, xterm).  

### swap between vertual terminals  
```bash
sudo chvt 1
# change to 1st terminal from other terminals
```  
```bash
sudo chvt 2
# change to 2nd terminal from other terminals
```  
```bash
sudo chvt 3
# change to 3rd terminal from other terminals
```  
```bash
sudo chvt 4
# change to 4th terminal from other terminals
```  
```bash
sudo chvt 5
# change to 5th terminal from other terminals
```  
```bash
sudo chvt 6
# change to 6th terminal from other terminals
```  
you can logout from current tty by just  
```bash
logout
```  
command this way it will not show that TTY even after
```bash
w
# command to check all logged in user with their tty
```  
command  
### **TTY Support Overview:**  
| **System**              | **Supports TTY (Ctrl + Alt + F1-F6)?** | **Notes** |
|------------------------|--------------------------------|---------|
| ✅ **Full Linux OS (Bare Metal Install)** | ✔ Yes | Works on both Red Hat & Debian-based distros. |
| ✅ **Linux in a VM (VirtualBox, VMware, KVM, etc.)** | ✔ Yes | Works if the VM has a virtual display. |
| ❌ **WSL (Windows Subsystem for Linux)** | ❌ No | Only pseudo-terminals (PTYs) available. |
| ✅ **Live Linux USB (Bootable Linux)** | ✔ Yes | Works just like a full Linux install. |

### **Why No TTY in WSL?**  
- **WSL is not a full Linux kernel** but a compatibility layer running inside Windows.  
- It **relies on Windows console APIs**, not real Linux virtual consoles.  

### **Alternatives in WSL:**  
Since `TTY1-TTY6` doesn’t exist, you can:  
1️⃣ **Open multiple WSL terminals** in Windows Terminal.  
2️⃣ **Use `tmux` or `screen`** to manage multiple terminal sessions inside one WSL window.  
