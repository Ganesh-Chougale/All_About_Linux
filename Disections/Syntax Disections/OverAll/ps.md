# `ps` : process  
## `ps` : shows active process (current shell session)  
```bash
ps
```  
#### Output:  
```console
    PID TTY          TIME CMD
   1053 pts/2    00:00:00 bash
   1118 pts/2    00:00:00 ps
```  
## `ps -au` : shows active process, (au: all users)  
- `a`: Show processes from all users (not just yours) but only those with a terminal.  
- `u`: Display user-oriented format (includes CPU%, memory%, etc.).  
```bash
ps -au
```  
#### Output:  
```console
USER         PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root         464  0.0  0.0   3160  1180 hvc0     Ss+  09:58   0:00 /sbin/agetty -o -p -- \u --noclear --keep-baud - 115200,3
root         544  0.0  0.1   6860  4672 pts/1    Ss   09:58   0:00 /bin/login -f
gorav        636  0.0  0.1   6072  5208 pts/1    S+   09:58   0:00 -bash
gorav        788  0.0  0.1   6200  5476 pts/2    Ss   10:21   0:00 -bash
root        1036  0.0  0.1   7264  4308 pts/2    S    11:07   0:00 su bro
bro         1053  0.0  0.1   6080  5168 pts/2    S    11:07   0:00 bash
bro         1126  100  0.1   8332  4248 pts/2    R+   11:19   0:00 ps -au
```  

## `ps aux` : shows active process, (aux: all users extended)  
- `a`: Show processes from all users (not just yours) but only those with a terminal.  
- `u`: Display user-oriented format (includes CPU%, memory%, etc.).    
- `x`: Include background processes (daemons, system services).  
```bash
 ps aux
```  
#### Output:  
```console
USER         PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root           1  0.0  0.3  22444 13596 ?        Ss   09:58   0:03 /sbin/init
root           2  0.0  0.0   2776  1924 ?        Sl   09:58   0:00 /init
root           6  0.0  0.0   2776   132 ?        Sl   09:58   0:00 plan9 --control-socket 7 --log-level 4 --server-fd 8 --pi
root          63  0.0  0.5  75076 23184 ?        S<s  09:58   0:02 /usr/lib/systemd/systemd-journald
root         106  0.0  0.1  25812  7416 ?        Ss   09:58   0:01 /usr/lib/systemd/systemd-udevd
root         127  0.0  0.0 227832  2216 ?        Ssl  09:58   0:00 snapfuse /var/lib/snapd/snaps/gnome-42-2204_202.snap /sna
root         128  0.0  0.0 227964  2200 ?        Ssl  09:58   0:00 snapfuse /var/lib/snapd/snaps/firefox_5783.snap /snap/fir
root         129  0.0  0.0 152936   180 ?        Ssl  09:58   0:00 snapfuse /var/lib/snapd/snaps/bare_5.snap /snap/bare/5 -o
root         134  0.0  0.0 153068   712 ?        Ssl  09:58   0:00 snapfuse /var/lib/snapd/snaps/core22_1748.snap /snap/core
root         135  0.0  0.4 601520 17484 ?        Ssl  09:58   0:04 snapfuse /var/lib/snapd/snaps/snapd_23545.snap /snap/snap
root         144  0.0  0.0 153068  2248 ?        Ssl  09:58   0:00 snapfuse /var/lib/snapd/snaps/gtk-common-themes_1535.snap
systemd+     164  0.0  0.2  21452 11812 ?        Ss   09:58   0:00 /usr/lib/systemd/systemd-resolved
systemd+     165  0.0  0.1  91044  6772 ?        Ssl  09:58   0:00 /usr/lib/systemd/systemd-timesyncd
root         228  0.0  0.1 308132  7360 ?        Ssl  09:58   0:00 /usr/libexec/accounts-daemon
avahi        229  0.0  0.1   8684  4100 ?        Ss   09:58   0:00 avahi-daemon: running [DESKTOP-DU9J3O1-2.local]
root         230  0.0  0.0   4236  2644 ?        Ss   09:58   0:00 /usr/sbin/cron -f -P
message+     231  0.0  0.1  10700  5748 ?        Ss   09:58   0:01 @dbus-daemon --system --address=systemd: --nofork --nopid
polkitd      235  0.0  0.2 384584 10392 ?        Ssl  09:58   0:00 /usr/lib/polkit-1/polkitd --no-debug
root         236  0.0  0.1 308188  6868 ?        Ssl  09:58   0:00 /usr/libexec/power-profiles-daemon
root         239  0.0  1.0 1395172 40904 ?       Ssl  09:58   0:01 /usr/lib/snapd/snapd
root         243  0.0  0.1 304536  4592 ?        Ssl  09:58   0:00 /usr/libexec/switcheroo-control
root         244  0.0  0.2  18156  8376 ?        Ss   09:58   0:00 /usr/lib/systemd/systemd-logind
root         246  0.0  0.3 468972 12996 ?        Ssl  09:58   0:00 /usr/libexec/udisks2/udisksd
root         252  0.0  0.4 1756096 16140 ?       Ssl  09:58   0:00 /usr/libexec/wsl-pro-service -vv
syslog       258  0.0  0.2 222508  9428 ?        Ssl  09:58   0:00 /usr/sbin/rsyslogd -n -iNONE
avahi        263  0.0  0.0   8420   360 ?        S    09:58   0:00 avahi-daemon: chroot helper
root         264  0.0  0.5 330812 19924 ?        Ssl  09:58   0:00 /usr/sbin/NetworkManager --no-daemon
root         265  0.0  0.1  17376  5748 ?        Ss   09:58   0:00 /usr/sbin/wpa_supplicant -u -s -O DIR=/run/wpa_supplicant
root         451  0.0  0.2  38788 11688 ?        Ss   09:58   0:00 /usr/sbin/cupsd -l
root         455  0.0  0.5 107048 22572 ?        Ssl  09:58   0:00 /usr/bin/python3 /usr/share/unattended-upgrades/unattende
root         464  0.0  0.0   3160  1180 hvc0     Ss+  09:58   0:00 /sbin/agetty -o -p -- \u --noclear --keep-baud - 115200,3
lp           475  0.0  0.1  16832  5640 ?        S    09:58   0:00 /usr/lib/cups/notifier/dbus dbus://
root         478  0.0  0.0  10976   700 ?        S    09:58   0:00 /usr/sbin/xrdp-sesman
lp           480  0.0  0.1  16832  5688 ?        S    09:58   0:00 /usr/lib/cups/notifier/dbus dbus://
cups-br+     481  0.0  0.4 268344 19708 ?        Ssl  09:58   0:00 /usr/sbin/cups-browsed
root         483  0.0  0.3 137380 15304 ?        Ssl  09:58   0:00 /usr/bin/sddm
xrdp         503  0.0  0.0  10128   720 ?        S    09:58   0:00 /usr/sbin/xrdp
root         510  0.0  0.1  14504  5728 ?        S    09:58   0:00 /usr/lib/xorg/Xorg -nolisten tcp -background none -seat s
root         544  0.0  0.1   6860  4672 pts/1    Ss   09:58   0:00 /bin/login -f
gorav        620  0.0  0.2  20400 11668 ?        Ss   09:58   0:00 /usr/lib/systemd/systemd --user
gorav        621  0.0  0.0  21176  1732 ?        S    09:58   0:00 (sd-pam)
gorav        632  0.0  0.2 103968 10656 ?        Ssl  09:58   0:00 /usr/bin/pipewire
gorav        633  0.0  0.1  92548  5580 ?        Ssl  09:58   0:00 /usr/bin/pipewire -c filter-chain.conf
gorav        634  0.0  0.4 399784 17372 ?        Ssl  09:58   0:00 /usr/bin/wireplumber
gorav        635  0.0  0.3 104208 12356 ?        Ssl  09:58   0:00 /usr/bin/pipewire-pulse
gorav        636  0.0  0.1   6072  5208 pts/1    S+   09:58   0:00 -bash
gorav        652  0.0  0.1   9440  4504 ?        Ss   09:58   0:00 /usr/bin/dbus-daemon --session --address=systemd: --nofor
rtkit        657  0.0  0.0  22940  1568 ?        SNsl 09:58   0:00 /usr/libexec/rtkit-daemon
root         785  0.0  0.0   2780   212 ?        Ss   10:21   0:00 /init
root         786  0.0  0.0   2780   216 ?        S    10:21   0:00 /init
gorav        788  0.0  0.1   6200  5476 pts/2    Ss   10:21   0:00 -bash
root        1036  0.0  0.1   7264  4308 pts/2    S    11:07   0:00 su bro
bro         1039  0.0  0.3  20564 11884 ?        Ss   11:07   0:00 /usr/lib/systemd/systemd --user
bro         1040  0.0  0.0  21180  1736 ?        S    11:07   0:00 (sd-pam)
bro         1051  0.0  0.2 103968  8444 ?        Ssl  11:07   0:00 /usr/bin/pipewire
bro         1052  0.0  0.1  92548  7704 ?        Ssl  11:07   0:00 /usr/bin/pipewire -c filter-chain.conf
bro         1053  0.0  0.1   6080  5168 pts/2    S    11:07   0:00 bash
bro         1054  0.0  0.4 399780 17160 ?        Ssl  11:07   0:00 /usr/bin/wireplumber
bro         1055  0.0  0.2 104208 10280 ?        Ssl  11:07   0:00 /usr/bin/pipewire-pulse
bro         1062  0.0  0.1   9432  4552 ?        Ss   11:07   0:00 /usr/bin/dbus-daemon --session --address=systemd: --nofor
bro         1127  0.0  0.1   8332  4256 pts/2    R+   11:19   0:00 ps aux
bro@DESKTOP-DU9J3O1:/home/gorav/Desktop$
```  

### **Summary**  
| Command       | Shows Processes From | Includes Daemons? | Includes Other Users? | Extra Details (CPU, MEM) |
|--------------|-------------------|------------------|----------------|------------------|
| `ps`         | Current terminal only | ❌ No            | ❌ No          | ❌ No |
| `ps -au`     | All users (with TTY)  | ❌ No            | ✅ Yes         | ✅ Yes |
| `ps aux`     | All processes (system-wide) | ✅ Yes | ✅ Yes | ✅ Yes |

👉 Use `ps aux` when you want a **complete** system-wide overview.  
👉 Use `ps -au` if you only care about **interactive (TTY) processes**.