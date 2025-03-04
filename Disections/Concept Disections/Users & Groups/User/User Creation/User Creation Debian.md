1. **Add a New User**  
   ```bash
   sudo adduser username
   ```
   - This command creates a new user and prompts for a password.
   - It also creates a home directory (`/home/username`).

2. **Set a Password** (If not set during user creation)  
   ```bash
   sudo passwd username
   ```

3. **Assign User to a Group**  
   ```bash
   sudo usermod -aG groupname username
   ```
   Example: Add the user to the `sudo` group (for admin privileges).  
   ```bash
   sudo usermod -aG sudo username
   ```

4. **Delete a User**  
   ```bash
   sudo deluser username
   ```
   - To remove the home directory along with the user:  
     ```bash
     sudo deluser --remove-home username
     ```

---
