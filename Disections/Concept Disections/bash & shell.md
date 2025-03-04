### **What is Bash?**  
Bash (**Bourne Again Shell**) is a **command-line interpreter** (shell) for Unix/Linux systems. It allows users to:  
- Run **commands** (e.g., `ls`, `cd`, `mkdir`).  
- Write **scripts** for automation.  
- Manage **processes and system tasks**.  

### **Is Bash Present in All Linux Distros?**  
**Mostly, Yes** – Bash is the **default shell** in many Linux distros, but not all.  

### **Shells Used in Popular Distros:**  
| Distro        | Default Shell |
|--------------|--------------|
| **Ubuntu/Debian**  | Bash (`/bin/bash`) |
| **RHEL/Fedora/CentOS** | Bash (`/bin/bash`) |
| **Arch Linux** | Bash (`/bin/bash`) |
| **Alpine Linux** | **ash** (`/bin/ash`) |
| **macOS** (older versions) | Bash (`/bin/bash`) |
| **macOS (newer)** | **Zsh** (`/bin/zsh`) |

### **How to Check Your Current Shell?**
```bash
echo $SHELL
```

### **Can I Use Other Shells?**
Yes! You can install and use different shells like:  
- **Zsh** (`zsh`) – More customization, used in macOS now.  
- **Fish** (`fish`) – User-friendly, auto-suggestions.  
- **Dash** (`dash`) – Lightweight, used in Debian scripts.  

Bash is common, but not **mandatory**. Some distros replace it with **lighter or more modern** shells.