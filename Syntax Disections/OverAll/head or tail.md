## tail or head for reading
### head  
```bash
head -3 /etc/passwd
```  
to tell that give me only first 3 lines of file  
#### Output:  
```vbnet
root:x:0:0:root:/root:/bin/bash
bin:x:1:1:bin:/bin:/sbin/nologin
daemon:x:2:2:daemon:/sbin:/sbin/nologin
```  
### tail  
```bash
tail -3 /etc/passwd
```  
to tell that give me only last 3 lines of file  
#### Output:  
```vbnet
tcpdump:x:72:72::/:/sbin/nologin
rserver:x:1000:1000:RHEL server:/home/rserver:/bin/bash
vboxadd:x:980:1::/var/run/vboxadd:/bin/false
```  

you can change the number from -3 to any number & it will give the output accordingly  