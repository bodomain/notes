Setting up a **t3.micro** instance with **SQLite** is a fantastic way to host a low-traffic project for virtually $0 under the AWS Free Tier. Since SQLite is just a file, you don't need to manage a heavy database engine like PostgreSQL or MySQL.

Here is your step-by-step guide to getting this running.

---

## 1. Launch the EC2 Instance
1.  Log into the [AWS Console](https://console.aws.amazon.com/).
2.  Navigate to **EC2** > **Instances** > **Launch Instance**.
3.  **Name:** Give your project a name.
4.  **OS:** Select **Amazon Linux 2023** (it’s lightweight and optimized).
5.  **Instance Type:** Select **t3.micro**. (Ensure it says "Free tier eligible").
6.  **Key Pair:** Create a new one and download the `.pem` file. **Don't lose this!**
7.  **Network Settings:** Check the boxes for **Allow SSH**, **Allow HTTP**, and **Allow HTTPS**.

---

## 2. Connect via SSH
Open your terminal (or PowerShell) and run the following command (replace the path and IP with yours):

```bash
chmod 400 your-key.pem
ssh -i "your-key.pem" ec2-user@your-instance-public-ip
```

---

## 3. Prepare the Environment & SQLite
Amazon Linux usually comes with SQLite installed, but let’s ensure everything is up to date and create a dedicated directory for your data.

```bash
# Update the system
sudo dnf update -y

# Create a project directory
mkdir ~/my-project && cd ~/my-project

# Verify sqlite3 is installed
sqlite3 --version
```

---

## 4. Create and Manage the Database
You can create your database file immediately. In SQLite, the "server" is just the library interacting with this file.



```bash
# Create (or open) your database file
sqlite3 production.db

# Inside the sqlite prompt, create a test table:
CREATE TABLE users (id INTEGER PRIMARY KEY, name TEXT);
INSERT INTO users (name) VALUES ('Gemini User');
.quit
```

---

## 5. Automated Backups (The "Simple" Way)
Since your database is just a file on the **EBS volume**, you can back it up by simply copying it. To do this properly without corrupting data (in case a write is happening), use the `.backup` command.

Let's create a simple backup script:
```bash
nano backup_db.sh
```
Paste this in:
```bash
#!/bin/bash
DATE=$(date +%Y-%m-%d_%H%M)
# Safely backup the database to a backup folder
sqlite3 /home/ec2-user/my-project/production.db ".backup /home/ec2-user/my-project/backup_$DATE.db"
echo "Backup created at $DATE"
```
*Note: For true safety, you should eventually move these backup files to an **S3 bucket** so they survive even if the EC2 instance is deleted.*

---

## 6. Security & Performance Tips
* **Permissions:** Ensure your web application has read/write access to the `.db` file AND the folder it sits in (SQLite needs folder write access to create temporary journal files).
    ```bash
    chmod 664 production.db
    chmod 775 ~/my-project
    ```
* **WAL Mode:** For better performance on EBS volumes, enable Write-Ahead Logging:
    ```bash
    sqlite3 production.db "PRAGMA journal_mode=WAL;"
    ```

---

### Important Reminder
While the **t3.micro** is "Free Tier" eligible, it's only free for **12 months** for new accounts. Also, keep an eye on your **EBS (Storage)** usage—the Free Tier covers up to 30GB.

Would you like me to help you write a **crontab** entry to automate those backups every night?







# LOGIN FROM OUTSIDE

Yes, you can, but by default, AWS disables password login for security. To login from another machine without the `.pem` file, you have three main options ranging from "fastest" to "most secure."

---

### Option 1: The "Cloud Way" (EC2 Instance Connect)
If you just need to access the machine from any browser, you don't need the `.pem` file at all.
1.  Go to the **AWS Console** > **Instances**.
2.  Select your instance and click the **Connect** button at the top.
3.  Choose **EC2 Instance Connect** and click **Connect**.
    * *Result:* A terminal opens directly in your browser. No files required.

---

### Option 2: The "Password Way" (Easiest but Less Secure)
You can set a traditional password for the `ec2-user`. **Warning:** This makes your instance vulnerable to "brute-force" attacks unless you also restrict your Security Group to only your IP address.

**Step 1: Set a password (while logged in with your .pem)**
```bash
sudo passwd ec2-user
# Enter a strong password twice
```

**Step 2: Enable password authentication in SSH settings**
```bash
sudo nano /etc/ssh/sshd_config
```
Find the line `PasswordAuthentication no` and change it to `yes`. (If it's commented out with a `#`, remove the `#`).

**Step 3: Restart the SSH service**
```bash
sudo systemctl restart sshd
```
*Result:* You can now login from any machine using `ssh ec2-user@3.64.194.11` and just typing your password.

---

### Option 3: The "Pro Way" (SSH Agent Forwarding)
If you want to move between your *own* machines without carrying the file, you can add the key to your "SSH Agent."

**On your main machine (where the .pem is):**
```bash
ssh-add your-key.pem
ssh -A ec2-user@3.64.194.11
```
The `-A` flag "forwards" your key. If you then connect to another machine from *that* terminal, your key travels with you securely in memory.

---

### Which should you choose?
* **Use Option 1** if you are at a library or a friend's house and just need to check something quickly.
* **Use Option 2** if you are building a tool that doesn't support SSH keys, but **be sure to update your Security Group** so that only *your* IP can attempt to login.



**Would you like me to help you set up that Security Group rule to "lock the door" so only your home IP can try the password?**