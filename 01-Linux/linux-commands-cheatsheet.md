# Linux Battle Cheat Sheet

**Date:** January 28, 2026

## 1. File System Operations
* `ls -lah`: List all files (including hidden) with file sizes.
* `pwd`: Print Working Directory (Where am I?).
* `cd /path`: Change directory.
* `mkdir -p folder/subfolder`: Create a folder tree (parent and child).
* `cp -r source dest`: Copy a folder recursively.
* `rm -rf folder`: Force remove a folder (Careful!).
* `mv source dest`: Move or Rename a file.
* `tail -f file.log`: **Follows** the file in real-time. Crucial for watching live error logs.
* `grep -r "error" .`: Search for the string "error" inside all files in current folder.
* `find / -name "config.xml"`: Search the entire drive for a specific file.
* `chmod 755 file`: Change file permissions (Owner: R+W+X, Group/Others: R+X).
* `chown user:group file`: Change file ownership.

## 2. System Performance & Disk
* `top`: Real-time view of processes (CPU/RAM usage).
* `df -h`: Check disk space usage (Free space on drive).
* `du -sh foldername`: **Disk Usage Summary**. Shows the total size of a specific folder in human-readable format (e.g., 500MB).
* `free -h`: Check available RAM.

## 3. Process Management
* `ps aux`: List all running processes.
* `ps aux | grep nginx`: Find the Process ID (PID) of Nginx.
* `kill <pid>`: Gracefully stop a process (SIGTERM - lets it save data).
* `kill -9 <pid>`: **Force Kill (SIGKILL)**. Stops the process immediately. Dangerous—use only if it's stuck.
* `systemctl status service`: Check if a service is running.

## 4. Networking
* `ip addr`: Show IP addresses (Replacement for `ifconfig`).
* `ping 8.8.8.8`: Check connectivity to the internet.
* `curl -v http://localhost`: Fetch a URL and see headers (Debug APIs).
* `netstat -tulpn`: Lists all **Listening Ports** and the PID of the program using them. (e.g., checks if Nginx is actually listening on port 80).