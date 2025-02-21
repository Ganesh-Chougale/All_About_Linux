### 1. know your WSL's IP  
#### Terminal:  
```bash
ip a
``` 
get the `ipnet` under `2: eth0:` & copy it.  
### **E.g:**  
#### Output:  
```vbnet
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet 10.255.255.254/32 brd 10.255.255.254 scope global lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host
       valid_lft forever preferred_lft forever
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1400 qdisc mq state UP group default qlen 1000
    link/ether 00:15:5d:b6:50:ae brd ff:ff:ff:ff:ff:ff
    inet 172.18.6.243/20 brd 172.18.15.255 scope global eth0
       valid_lft forever preferred_lft forever
    inet6 fe80::215:5dff:feb6:50ae/64 scope link
       valid_lft forever preferred_lft forever
```  
then `172.18.6.243` this is our IP address  

### 2. Open `Remote Desktop Connection` in windows  
- A. via Run  
Press `Win + R` to open the Run dialog.  
```bash
mstsc
```  
Press Enter.  

- B. Using Search  
Press `Win + S` and search for "**Remote Desktop Connection**".  
Click on the Remote Desktop Connection app.  

### 3. Connect WSL & Windows  
paste the copied ip address of WSL  
after that use rightful credintials & enjoy th GUI  