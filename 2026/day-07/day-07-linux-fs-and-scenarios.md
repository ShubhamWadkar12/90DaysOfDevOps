# Day 07 – Linux File System & Troubleshooting Scenarios

## Part 1: Linux File System Hierarchy

### Core Directories (Must Know)

### `/` (root)
- Starting point of the Linux filesystem; everything lives under this.
- Seen folders: `bin/`, `etc/`, `home/`
- I would use this when understanding overall system structure.

---

### `/home`
- Contains home directories for normal users.
- Seen folders: `shubham/`
- I would use this when working with user files, scripts, and configs.

Command:
ls -la ~

---

### `/root`
- Home directory of the root (admin) user.
- Seen files: `.bashrc`, `.ssh/`
- I would use this when performing admin-level tasks as root.

---

### `/etc`
- Stores system-wide configuration files.
- Seen files/folders: `hostname`, `ssh/`
- I would use this when modifying system or service configuration.

Command:
cat /etc/hostname

---

### `/var/log`
- Contains logs for system and services (very important for DevOps).
- Seen files: `syslog`, `auth.log`
- I would use this when debugging issues or service failures.

Command:
du -sh /var/log/* 2>/dev/null | sort -h | tail -5

---

### `/tmp`
- Temporary files used by applications.
- Files here are often deleted after reboot.
- I would use this when testing or storing short-lived files.

---

### Additional Directories (Good to Know)

### `/bin`
- Essential system command binaries.
- Seen commands: `ls`, `cp`
- I would use this when system is in minimal or recovery mode.

---

### `/usr/bin`
- User-level command binaries.
- Seen commands: `python3`, `git`
- I would use this when running normal applications.

---

### `/opt`
- Optional or third-party applications.
- Seen folders: vendor or custom apps
- I would use this when installing manual or external software.

---

## Part 2: Scenario-Based Practice

### Scenario 1: Service Not Starting

Problem: A service called `myapp` failed to start after reboot.

Step 1:
systemctl status myapp  
Why: Check whether the service is running, failed, or stopped.

Step 2:
journalctl -u myapp -n 50  
Why: View recent logs to identify the failure reason.

Step 3:
systemctl is-enabled myapp  
Why: Check if the service is enabled to start on boot.

Step 4:
systemctl restart myapp  
Why: Try restarting the service after inspection.

What I learned:
Always check service status first, then logs, then boot configuration.

---

### Scenario 2: High CPU Usage

Problem: Application server is slow.

Step 1:
top  
Why: View live CPU usage and identify high-CPU processes.

Step 2:
ps aux --sort=-%cpu | head -10  
Why: List top CPU-consuming processes.

Step 3:
top -p <PID>  
Why: Monitor a specific problematic process.

What I learned:
Identify the process first before attempting fixes.

---

### Scenario 3: Finding Service Logs

Problem: Developer asks where Docker service logs are.

Step 1:
systemctl status docker  
Why: Confirm service name and current status.

Step 2:
journalctl -u docker -n 50  
Why: View recent Docker logs.

Step 3:
journalctl -u docker -f  
Why: Follow logs in real time.

What I learned:
systemd services store logs in journald.

---

### Scenario 4: File Permission Issue

Problem: `/home/user/backup.sh` shows "Permission denied".

Step 1:
ls -l /home/user/backup.sh  
Why: Check current file permissions.

Step 2:
chmod +x /home/user/backup.sh  
Why: Add execute permission.

Step 3:
ls -l /home/user/backup.sh  
Why: Verify execute permission is added.

Step 4:
./backup.sh  
Why: Run the script.

What I learned:
Scripts must have execute (`x`) permission to run.

---

## Final Takeaway

- Linux troubleshooting follows a flow: observe → verify → fix
- Logs are critical for debugging
- Never assume — always check first
