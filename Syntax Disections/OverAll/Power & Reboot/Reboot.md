## **`reboot` – Restart the System**  
🔹 Immediately reboots the system.  

**Usage:**  
```sh
reboot
```
or  
```sh
sudo reboot
```
✔ Equivalent to:  
```sh
shutdown -r now
```
✔ Can force a reboot if needed:  
```sh
sudo reboot --force
```

⚠️ **On systemd-based distros (Ubuntu, RHEL 7+, Debian 10+), use `systemctl` instead:**  
```sh
systemctl reboot
```