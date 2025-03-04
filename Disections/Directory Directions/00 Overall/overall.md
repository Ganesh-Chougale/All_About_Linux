The Linux file system follows a hierarchical structure where everything starts from the **root (`/`) directory**. Below is an overview of the key directories and their purposes:
```bash
cd /
```  
```sh
/
├── bin     → Essential command binaries (e.g., `ls`, `cp`, `mv`)
├── boot    → Bootloader files (e.g., kernel, `grub`)
├── dev     → Device files (e.g., `sda`, `tty`)
├── etc     → Configuration files (e.g., network, user settings)
├── home    → User home directories (`/home/user`)
├── lib     → Essential shared libraries for binaries in `/bin` and `/sbin`
├── media   → Mount points for removable media (USB, CD-ROM)
├── mnt     → Temporary mount points for external filesystems
├── opt     → Optional software (e.g., third-party apps)
├── proc    → Virtual filesystem for process and system info
├── root    → Home directory for the root user
├── run     → Runtime variable data (e.g., PID files, sockets)
├── sbin    → System binaries (e.g., `fdisk`, `shutdown`)
├── srv     → Data for services like web servers (`/srv/http`)
├── tmp     → Temporary files (cleared on reboot)
├── usr     → User binaries, libraries, and documentation
│   ├── bin  → User binaries (e.g., `nano`, `gcc`)
│   ├── lib  → Libraries for `/usr/bin` and `/usr/sbin`
│   ├── local → Locally installed software
│   ├── share → Architecture-independent data (e.g., icons)
│   ├── src  → Source code for packages
├── var     → Variable data like logs, caches, and databases
│   ├── log  → System logs (`/var/log/syslog`)
│   ├── cache → Cached files
│   ├── spool → Queued jobs (e.g., print jobs, mail)
│   ├── www  → Web server files (`/var/www/html`)
```