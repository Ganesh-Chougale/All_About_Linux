### **Normal User vs. Super User**  

| Feature          | Normal User | Super User (Root) |
|-----------------|------------|-------------------|
| **Permissions**  | Limited access (restricted to their own files and processes) | Full system access (can modify system files and settings) |
| **Command Execution** | Cannot run administrative commands | Can execute any command using `sudo` or as root |
| **User Management** | Cannot create, delete, or modify users | Can create, delete, and modify users and groups |
| **File System Access** | Cannot access system-critical directories like `/root`, `/etc`, `/var` | Has access to all files and directories |
| **Software Installation** | Can only install software in home directory (if permissions allow) | Can install, update, and remove system-wide software |
| **Security Risks** | Safer, as they cannot harm the system | Risky if commands are misused (e.g., `rm -rf /`) |
| **Execution of System Processes** | Cannot start/stop system services | Can start, stop, and modify system services (e.g., `systemctl restart apache2`) |

### **How to Switch Between Normal and Super User**  
- Use `sudo` before a command to temporarily gain superuser privileges:
  ```sh
  sudo apt update
  ```
- Switch to the root user with:
  ```sh
  sudo su
  ```
  (Requires password)
- To switch back, type:
  ```sh
  exit
  ```  