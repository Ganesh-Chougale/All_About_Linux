### **1. Install OpenSSH Server**  
Run the following command to install the SSH server:  
```bash
sudo apt update && sudo apt install -y openssh-server
```  

### **2. Check SSH Service Status**  
After installation, check if the SSH service is running:  
```bash
systemctl status ssh
```  
- If it says **"active (running)"**, SSH is already running.  
- If not, start it manually:  
  ```bash
  sudo systemctl start ssh
  ```  

### **3. Enable SSH to Start on Boot**  
To ensure SSH starts automatically after a reboot:  
```bash
sudo systemctl enable ssh
```  

### **4. Allow SSH Through Firewall (if applicable)**  
If you're using **UFW (Uncomplicated Firewall)**, allow SSH connections:  
```bash
sudo ufw allow ssh
sudo ufw enable
sudo ufw status
```  

### **5. Connect to the SSH Server**  
Now, you can connect to your Ubuntu machine using:  
```bash
ssh username@your-server-ip
```  
Replace `username` with your actual Ubuntu user and `your-server-ip` with your system's IP.  

### **6. (Optional) Secure SSH**  
To improve security, edit the SSH configuration file:  
```bash
sudo nano /etc/ssh/sshd_config
```
- Change **port** (default is 22)  
- Disable **root login** (`PermitRootLogin no`)  
- Allow only specific users (`AllowUsers youruser`)  

Restart SSH to apply changes:  
```bash
sudo systemctl restart ssh
```  