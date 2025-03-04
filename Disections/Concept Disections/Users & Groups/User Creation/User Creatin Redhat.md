1. **Add a New User**  
   ```bash
   sudo useradd -m username
   ```
   - `-m` ensures that a home directory (`/home/username`) is created.

2. **Set a Password**  
   ```bash
   sudo passwd username
   ```

3. **Assign User to a Group**  
   ```bash
   sudo usermod -aG groupname username
   ```
   Example: Add the user to the `wheel` group (for admin privileges).  
   ```bash
   sudo usermod -aG wheel username
   ```

4. **Delete a User**  
   ```bash
   sudo userdel username
   ```
   - To remove the home directory along with the user:  
     ```bash
     sudo userdel -r username
     ```