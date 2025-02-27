### **1️⃣ Common Steps (For All OSes)**
1. Open **VirtualBox Manager**  
2. Select your VM → **Settings** → **General** → **Advanced**  
3. Set:  
   - **Shared Clipboard** → **Bidirectional**  
   - **Drag’n’Drop** → **Bidirectional**  
4. Click **OK**, then **start your VM**  

---

### **2️⃣ OS-Specific Steps**  

#### **📌 Windows Guest VM**  
1. Start Windows VM  
2. In **VirtualBox menu**, go to:  
   **Devices → Insert Guest Additions CD Image**  
3. Open **File Explorer** → Run `VBoxWindowsAdditions.exe` → Install & Restart  

---

#### **📌 Ubuntu/Debian-Based Linux (Ubuntu, Mint, Pop!_OS, Kali, etc.)**  
1. Open terminal and install dependencies:  
   ```sh
   sudo apt update
   sudo apt install build-essential dkms -y
   ```
2. In VirtualBox, go to **Devices → Insert Guest Additions CD Image**  
3. Run these commands:  
   ```sh
   sudo mount /dev/cdrom /mnt
   sudo /mnt/VBoxLinuxAdditions.run
   reboot
   ```

---

#### **📌 RHEL-Based Linux (CentOS, AlmaLinux, Rocky, Fedora, etc.)**  
1. Open terminal and install dependencies:  
   ```sh
   sudo dnf install epel-release -y  
   sudo dnf install kernel-devel kernel-headers gcc make perl -y
   ```
2. In VirtualBox, go to **Devices → Insert Guest Additions CD Image**  
3. Run these commands:  
   ```sh
   sudo mount /dev/cdrom /mnt
   sudo /mnt/VBoxLinuxAdditions.run
   reboot
   ```

---

#### **📌 Arch Linux / Manjaro**  
1. Install required packages:  
   ```sh
   sudo pacman -S virtualbox-guest-utils
   ```
2. Start VirtualBox Guest Services:  
   ```sh
   sudo systemctl enable --now vboxservice.service
   ```
3. Reboot your VM:  
   ```sh
   reboot
   ```

---

#### **📌 macOS Guest VM (Limited Support)**  
1. Enable clipboard in **VirtualBox Settings → General → Advanced**  
2. macOS Guest Additions are **not officially supported**, so clipboard may not work fully.  
3. Use **shared folders or SSH (scp, rsync)** as a workaround.  

---

### **3️⃣ Verify Clipboard Sharing**
✅ Copy-paste text **between host & VM**  
✅ Try **drag-and-drop** between host & VM  