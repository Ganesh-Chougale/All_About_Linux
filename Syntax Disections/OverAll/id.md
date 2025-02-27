### **`id`**:  
`id` → tells the Ids & info of user.  
```bash
id
```  
#### Output:  
```vbnet
uid=1000(gorav) gid=1000(gorav) groups=1000(gorav),4(adm),20(dialout),24(cdrom),25(floppy),27(sudo),29(audio),30(dip),44(video),46(plugdev),100(users),107(netdev)
```  
### check if the user have root previllages or not
```bash
sudo id
```  
#### Output:  
```vbnet
uid=0(root) gid=0(root) groups=0(root)
```  
`uid=0` always indicates that user is root  
## switch to root user & check  
```bash
sudo -i
```  
```bash
id
```  
#### Output:  
```vbnet
uid=0(root) gid=0(root) groups=0(root)
```  