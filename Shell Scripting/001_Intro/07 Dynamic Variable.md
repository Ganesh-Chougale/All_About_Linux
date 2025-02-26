we can assign dynamic value to a variable, such as `hostname`, `date` etc., this will helps us in dynamic scriptings.  
```bash
vi 05_dyn_vars.sh
```  
inside file  
```bash
#!/bin/bash

hostname_var=$(hostname)  
date_var=$(date)  
user_var=$USER  
uptime_var=$(uptime -p)  

echo "Hostname: $hostname_var"
echo "Current Date: $date_var"
echo "Logged-in User: $user_var"
echo "System Uptime: $uptime_var"
```  
save & run  
#### Output:  
```vbnet
Hostname: DESKTOP-DU9J3O1
Current Date: Sat Feb 22 15:55:43 IST 2025
Logged-in User: gorav
System Uptime: up 8 minutes
```  

✅ `$(command)` stores output in a variable.  
✅ Variables hold dynamic values for later use.  