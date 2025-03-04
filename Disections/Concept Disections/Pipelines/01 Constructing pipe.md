### **Constructing Pipelines in Linux**  
A **pipeline** in Linux connects multiple commands using the **`|` (pipe) operator**, allowing the output of one command to become the input for another.

---

### **Basic Syntax:**  
```bash
command1 | command2 | command3 ...
```
- `command1` → Produces output.  
- `command2` → Takes `command1`'s output as input.  
- `command3` → Takes `command2`'s output, and so on.  

---

## **🔹 Practical Examples**
### **1️⃣ Filtering Output**  
```bash
ls -l | grep ".sh"
```
- `ls -l` → Lists files with details.  
- `grep ".sh"` → Filters only files ending with `.sh`.  

### **2️⃣ Counting Matching Lines**  
```bash
cat file.txt | grep "error" | wc -l
```
- `cat file.txt` → Displays file contents.  
- `grep "error"` → Finds lines containing `"error"`.  
- `wc -l` → Counts those lines.  

### **3️⃣ Sorting & Removing Duplicates**  
```bash
cat names.txt | sort | uniq
```
- `sort` → Sorts the lines alphabetically.  
- `uniq` → Removes duplicate lines.  

### **4️⃣ Finding Top 5 Processes by Memory Usage**  
```bash
ps aux | sort -k4 -nr | head -5
```
- `ps aux` → Lists all processes.  
- `sort -k4 -nr` → Sorts by memory usage (column 4) in descending order.  
- `head -5` → Shows the top 5 processes.  

---

### **🔹 Combining Redirections & Pipelines**  
Pipelines (`|`) only work with **stdout**, but you can include `stderr` by redirecting it:  
```bash
command 2>&1 | another_command
```
- `2>&1` → Redirects **stderr** (`2>`) to **stdout** (`1`), so both are piped forward.  

**Example:**  
```bash
ls /root /home 2>&1 | grep "Permission denied"
```
- Lists `/root` & `/home`.  
- Redirects errors to stdout.  
- Filters for `"Permission denied"` errors.  

---

`Note` : standard `output` of previous command is standard `input` of next command after pipe (|) sign.