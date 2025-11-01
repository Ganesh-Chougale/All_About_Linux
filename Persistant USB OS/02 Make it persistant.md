## 1. know the partitions  
- list all storage unit  
```bash
lsblk
```  
it will show usb partitions like this  
`loop0`  
`sda1`, `sda2`...   
`sdx<n>`  
mostly only 2 or 3.  
`loop0` (or similiar) is where os is installed & other partitions are spared ones  

## 2. create new persistant partition  
```bash
sudo fdisk /dev/sdX
```  
here  `X` replace your sd letter (usually letter `b` in most cases)  
- it will give warning message that partition is in use & re-partitioning is bad idea.
`note`: i had ssd & usb. both were 256gb & i choose accidently sd`a` deleting my ssd C drive, so choose last letter carefully. make it sure that it belongs to USB  
```bash
n
```  
type `n` just skip it . 
- select default  

```bash
select (default) p:
# p stands for primary partition
# just press enter
```  
- select partition number  
```bash
select number(num1, num2.., defualt <>):
# select default (usually 3)
```  
- choose default first sector 
```bash
First sector (number - number, default number): 
# press enter
```  
- choose default last sector 
```bash
Last sector <some long message>: 
# press enter
```  
- write changes  
```bash
Command (m for help): w
# press w to write
```  
this creates partition & sync disk  

## 3. check partitions again  
```bash
lsblk
```  
now you will one more partition  

## 4. format partition  
```bash
sudo mkfs.ext4 -L persistence /dev/sdx<>
# replace <> with last digit which newly created partition number
```  
```bash
create journal:
# press enter with defaults
```  
wait for some time it will setup everything  

## 5. create new directory to use  
```bash
sudo mount /dev/sdX<> /mnt/my_usb
# replace <> with last digit which newly created partition number
```  

## 6. make directory persistant  
- this will keep files intact after rebooting system  
```bash
 echo "/ union" | sudo tee /mnt/my_usb/persistence.conf
```  
it will print `union`  
-  This command safely disconnects the USB (or other device) mounted at /mnt/my_usb from the system, so it can be removed without risking data
```bash
sudo umount /mnt/my_usb
```  

## 7. test the persistancy  
- create some files or folder or desktop
- reboot system
- choose `live system with USB persistance`  
- check if they persist or not
`note`: sometime perstistancy won't work at first or even some case 2nd reboot.  