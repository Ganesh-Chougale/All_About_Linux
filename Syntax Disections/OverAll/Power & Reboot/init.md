## **`init` – Change System Runlevel (Advanced Shutdown/Restart Method)**  
🔹 `init` controls the **runlevels** (system states).  

**Usage:**  
```sh
init 0  # Power off
init 6  # Reboot
```

| Runlevel | Purpose |
|----------|---------|
| `0` | Halt (Shutdown) |
| `1` | Single-user mode (Recovery) |
| `3` | Multi-user mode (No GUI) |
| `5` | Multi-user mode with GUI |
| `6` | Reboot |