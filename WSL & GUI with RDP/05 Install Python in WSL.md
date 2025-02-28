## A. `Install Python in WSL`  
### **1. Open WSL Terminal**  
Press `Win + R`, type `wsl`, and hit **Enter** to open the WSL terminal.

### **2. Update Package Lists**  
Run the following command to update your package lists:  
```bash
sudo apt update && sudo apt upgrade -y
```

### **3. Install Python**  
Run:  
```bash
sudo apt install python3 python3-pip -y
```

### **4. Verify Installation**  
Check the installed version of Python:  
```bash
python3 --version
```

Check pip version (optional):  
```bash
pip3 --version
```

### **5. Set Python3 as Default (Optional)**  
If `python` command is not recognized, create a symlink:  
```bash
sudo ln -s /usr/bin/python3 /usr/bin/python
```
Now, you can run `python` instead of `python3`.

## B. `Use a Virtual Environment (if error occures for further operations)`  
You're seeing the **"externally-managed-environment"** error because **Ubuntu in WSL** uses a system-managed Python environment that prevents direct installations with `pip`.  

### **✅ Solution: Use a Virtual Environment (Recommended)**
1. **install virtual environment:**
    ```bash
    apt install python3.12-venv
    ```  
2. **Create a virtual environment:**  
   ```sh
   python3 -m venv myenv
   ```
3. **Activate the environment:**  
   ```sh
   source myenv/bin/activate
   ```
4. **Install `gdown` inside it:**  
   ```sh
   pip install gdown
   ```