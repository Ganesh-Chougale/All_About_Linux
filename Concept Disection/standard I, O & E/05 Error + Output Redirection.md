### 4. Error + Output Redirection `&>`  
`Error` + `output` -----> `samefile.txt`  
```bash
find /etc/ -name passwd &> samefile.txt
```  
##### Preview:  
![](../z_images/014.png)  


& if we just use `&>>` instead of `&>` it will both save & append errors & output.  
```bash
find /etc/ -name passwd &>> samefile.txt
```  
##### Preview:  
![](../z_images/015.png)  