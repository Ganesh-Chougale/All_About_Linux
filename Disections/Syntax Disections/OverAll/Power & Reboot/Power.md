## **`poweroff` – Shut Down the System**  
🔹 Immediately shuts down the system and turns off the machine.  

**Usage:**  
```sh
poweroff
```
or  
```sh
sudo poweroff
```
✔ Works in **both systemd and SysVinit-based systems** (Red Hat, Debian, Ubuntu, etc.).  
✔ Equivalent to:  
```sh
shutdown -h now
```

⚠️ **On systemd-based distros (Ubuntu, RHEL 7+, Debian 10+), use `systemctl` instead:**  
```sh
systemctl poweroff
```