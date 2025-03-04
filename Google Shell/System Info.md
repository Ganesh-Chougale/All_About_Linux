OS, destroy, version  
Ram  
Rom  
storage  
other specs  
### **1. OS, Distro & Version**  
- **Distro Name & Version**  
  ```bash
  cat /etc/os-release
  ```
- **Kernel Version**  
  ```bash
  uname -r
  ```
- **Full System Info**  
  ```bash
  uname -a
  ```

### **2. RAM Details**  
- **Total & Free RAM**  
  ```bash
  free -h
  ```
- **Detailed RAM Info**  
  ```bash
  cat /proc/meminfo
  ```

### **3. Storage (HDD/SSD & Partitions)**  
- **Disk Usage (Human Readable)**  
  ```bash
  df -h
  ```
- **List All Drives & Partitions**  
  ```bash
  lsblk
  ```
- **Detailed Disk Info**  
  ```bash
  sudo fdisk -l
  ```

### **4. CPU Info**  
- **CPU Model & Details**  
  ```bash
  lscpu
  ```

### **5. Other Hardware Details**  
- **Full System Info**  
  ```bash
  sudo lshw -short
  ```
- **Check Connected USB Devices**  
  ```bash
  lsusb
  ```
- **Check PCI Devices (Graphics, Network, etc.)**  
  ```bash
  lspci
  ```