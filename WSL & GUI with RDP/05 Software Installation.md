You can install **Google Chrome** on Ubuntu using two methods: **GUI (Graphical)** and **Terminal (CLI)**.  

---

### **Method 1: Using Terminal (Recommended)**
#### **Step 1: Download the Chrome `.deb` package**
Run the following command to download the latest stable version of Google Chrome:

```bash
wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
```

#### **Step 2: Install Google Chrome**
Use the `dpkg` command to install the downloaded package:

```bash
sudo dpkg -i google-chrome-stable_current_amd64.deb
```

If there are dependency errors, fix them using:

```bash
sudo apt --fix-broken install
```

#### **Step 3: Verify Installation**
Run the following command to check if Chrome is installed:

```bash
google-chrome --version
```

#### **Step 4: Launch Google Chrome**
You can start Chrome using:

```bash
google-chrome
```
or  
Find **Google Chrome** in the **Applications Menu**.

---

### **Method 2: Using GUI (Graphical)**
1. **Download Chrome:**  
   - Open Firefox (default browser).  
   - Visit [Google Chrome Download Page](https://www.google.com/chrome/).  
   - Download the **.deb** package for Ubuntu.  

2. **Install Chrome:**  
   - Locate the downloaded `.deb` file (usually in `Downloads`).  
   - Double-click the file and open it with **Ubuntu Software**.  
   - Click **Install** and enter your password if prompted.  

3. **Launch Chrome:**  
   - Open **Activities** > Search for **Google Chrome** > Click to launch.  

---

### **Optional: Make Chrome Default Browser**
```bash
xdg-settings set default-web-browser google-chrome.desktop
```
