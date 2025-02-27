A Linux command generally has three parts:  

1. **Command** – The actual command you run (e.g., `ls`, `cp`, `rm`).  
2. **Option** – Modifies the behavior of the command (e.g., `-l` for long format in `ls -l`).  
3. **Argument** – The target on which the command operates (e.g., a filename or directory).  

Example:  
```bash
ls -l /home
```
- `ls` → Command  
- `-l` → Option (long format)  
- `/home` → Argument (target directory)  

### **E.g:**  
1. **List files in a directory**  
   ```bash
   ls
   ```
   - Command: `ls`  
   - No option or argument (lists files in the current directory)  

2. **List files in long format**  
   ```bash
   ls -l
   ```
   - Command: `ls`  
   - Option: `-l` (long format)  
   - No argument  

3. **List files in a specific directory**  
   ```bash
   ls /home
   ```
   - Command: `ls`  
   - No option  
   - Argument: `/home` (directory)  

4. **Copy a file**  
   ```bash
   cp file1.txt file2.txt
   ```
   - Command: `cp` (copy)  
   - No option  
   - Arguments: `file1.txt` (source), `file2.txt` (destination)  

5. **Remove a file with confirmation**  
   ```bash
   rm -i file.txt
   ```
   - Command: `rm` (remove)  
   - Option: `-i` (interactive, asks for confirmation)  
   - Argument: `file.txt`  

6. **Display the contents of a file**  
   ```bash
   cat file.txt
   ```
   - Command: `cat`  
   - No option  
   - Argument: `file.txt` (file to display)  

some time we `command` only, some time we run `command` `+` `option` sometimes we run `command` `+` `option` `+` `argument` or multiple arguments.  
its just the combination of things where commands remains mandatory while every other aspect changes.  

| Case | Example | Command | Option(s) | Argument(s) |
|------|---------|---------|----------|-------------|
| **1. Only command** | `ls` | `ls` | (none) | (none) |
| **2. Command + Option(s)** | `ls -l` | `ls` | `-l` | (none) |
| **3. Command + Argument(s)** | `ls /home` | `ls` | (none) | `/home` |
| **4. Command + Option(s) + Argument(s)** | `ls -l /home` | `ls` | `-l` | `/home` |
| **5. Command + Multiple Arguments** | `cp file1.txt file2.txt` | `cp` | (none) | `file1.txt`, `file2.txt` |
| **6. Command + Multiple Options + Argument(s)** | `rm -i -v file.txt` | `rm` | `-i`, `-v` | `file.txt` |