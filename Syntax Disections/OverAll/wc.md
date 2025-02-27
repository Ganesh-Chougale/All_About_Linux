## **`wc`**:  
`wc` → gives counts inside file.  
```bash
wc /etc/passwd
```  
#### Output:  
```vbnet
  36   83 2014 /etc/passwd
```  
1. **36** → Number of lines in the file (`/etc/passwd`).
2. **83** → Number of words in the file.
3. **2014** → Number of bytes in the file (file size).
4. **/etc/passwd** → The filename.

### `wc -l /etc/passwd` → Count lines only.
```bash
wc -l /etc/passwd
```  
#### Output:  
```vbnet
  36 /etc/passwd
```  
### `wc -w /etc/passwd` → Count words only.
```bash
wc -w /etc/passwd
```  
#### Output:  
```vbnet
83 /etc/passwd
```  
### `wc -c /etc/passwd` → Count bytes (file size).
```bash
wc -c /etc/passwd
```  
#### Output:  
```vbnet
2014 /etc/passwd
```  