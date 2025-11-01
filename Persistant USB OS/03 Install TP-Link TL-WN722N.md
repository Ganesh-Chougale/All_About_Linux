## 1. Update References  
```bash
sudo apt update
```  
## 2. Check if monitor mode enable  
```bash
sudo wifite
```  
read the log & if you find  
`Enabling monitor mode on wlan0... enabled!`  
then congratulations you have v1 adapter & dont need to install any additional drivers to monitor, injection or handshake mode  
if the message is  
`Enabling monitor mode on wlan0... failed!`  
the main issue is you are having latest adapter probablt v2 or v3  
so we need to install supporting drivers manually  
```bash
sudo wifite --kill
# to stop all conficting processes  
```  
## 3. Check the all UBS  
```bash
lsusb
#  ls + usb = list usb
```  
you will see all conntected USB including WIFI adapter  
now copy the box bracket part probably something like this:  
`[Realtek RTL8188EUS]`  
this is the name of that wifi adapter chipset, we need to make string from it  
to make it: remove box bracket, lowercase all leters & replace middle whitespace with `-`  
`realtek-rtl8188eus` make it from your individualt output  
## 4. install the drivers  
```bash
sudo apt install -y realtek-rtl8188eus-dkms
```  
## 5. reboot the system  
```bash
sudo shutdown -r  now
```  
## 6. Verify  
```bash
lsusb
```  
```bash
sudo wifite --kill
```   
