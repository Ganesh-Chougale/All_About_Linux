You can create a `git_push.sh` script that automates pushing code to the **main branch** with a commit message that includes the **current date and time**. Follow these steps:

---

### **Step 1: Create `git_push.sh` Script**
Run the following command to create and open the script:

```bash
nano git_push.sh
```

Paste the following code inside:

```bash
#!/bin/bash

# Get current date and time in format: DD-MM-YYYY / HH:MM AM/PM
TIMESTAMP=$(date +"%d-%m-%Y / %I:%M%p")

# Add all changes
git add .

# Commit with date & time as message
git commit -m "$TIMESTAMP"

# Push to main branch
git push origin main
```

---

### **Step 2: Make the Script Executable**
Run the following command to give execute permissions:

```bash
chmod +x git_push.sh
```

---

### **Step 3: Automate with a Git Hook (Optional)**
If you want this script to run automatically when you try to push manually, add it as a **pre-push hook**.

```bash
mv git_push.sh .git/hooks/pre-push
```

Now, every time you run `git push`, it will execute automatically.

---

### **Step 4: Run the Script Manually**
If you want to push manually, simply run:

```bash
./git_push.sh
```

This will:
✅ **Stage all changes**  
✅ **Commit with date & time**  
✅ **Push to the main branch**  
