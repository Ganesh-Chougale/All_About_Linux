### **`grep`**:  
### **`grep` Command in Linux**  

The `grep` (Global Regular Expression Print) command is used for searching and filtering text using patterns or regular expressions. It scans input line by line and prints matching lines.

---

### **Basic Syntax**  
```bash
grep [OPTIONS] PATTERN [FILE...]
```
- `PATTERN` – The text or regex pattern to search for.
- `FILE` – The file(s) where the search is performed.

---

### **Common Use Cases**
#### **1. Search for a word in a file**
```bash
grep "error" /var/log/syslog
```
🔹 Finds all lines containing `"error"` in `/var/log/syslog`.

#### **2. Case-insensitive search (`-i`)**
```bash
grep -i "warning" logs.txt
```
🔹 Matches `warning`, `WARNING`, `WaRnInG`, etc.

#### **3. Display line numbers (`-n`)**
```bash
grep -n "failed" auth.log
```
🔹 Shows matching lines with line numbers.

#### **4. Search recursively in directories (`-r` or `-R`)**
```bash
grep -r "TODO" /home/user/projects/
```
🔹 Searches for `"TODO"` in all files inside `/home/user/projects/`.

#### **5. Show only matching words (`-o`)**
```bash
grep -o "success" output.log
```
🔹 Prints only occurrences of `"success"`, not the full lines.

#### **6. Count matches (`-c`)**
```bash
grep -c "user" /etc/passwd
```
🔹 Shows how many times `"user"` appears in `/etc/passwd`.

#### **7. Invert match (`-v`)**
```bash
grep -v "debug" app.log
```
🔹 Shows lines that **do not** contain `"debug"`.

#### **8. Match full words only (`-w`)**
```bash
grep -w "root" /etc/passwd
```
🔹 Matches `root` but not `root123` or `superroot`.

#### **9. Use regex patterns (`-E`)**
```bash
grep -E "error|failed|warning" logs.txt
```
🔹 Searches for `"error"`, `"failed"`, or `"warning"`.

#### **10. Find lines starting with a pattern (`^`)**
```bash
grep "^root" /etc/passwd
```
🔹 Matches lines that start with `"root"`.

#### **11. Find lines ending with a pattern (`$`)**
```bash
grep "bash$" /etc/passwd
```
🔹 Finds users with `/bin/bash` as their shell.

---

### **Combination with Other Commands**
1. **Search running processes**
```bash
ps aux | grep "apache"
```
🔹 Finds Apache processes.

2. **Filter output from `ls`**
```bash
ls -l | grep ".txt"
```
🔹 Lists only `.txt` files.

3. **Monitor logs in real-time**
```bash
tail -f /var/log/syslog | grep "error"
```
🔹 Shows live updates of log files, filtering for `"error"`.

---

### **Summary Table**
| Option | Description |
|--------|-------------|
| `-i`   | Case-insensitive search |
| `-n`   | Show line numbers |
| `-r`   | Recursive search in directories |
| `-o`   | Show only matched words |
| `-c`   | Count matches |
| `-v`   | Invert match (exclude) |
| `-w`   | Match whole words only |
| `-E`   | Use extended regex |