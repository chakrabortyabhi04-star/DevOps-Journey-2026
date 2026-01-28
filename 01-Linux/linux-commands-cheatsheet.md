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

Part 1: The Interview "Heat" Answers
Q1: The Log File Scenario

Question: The app is crashing. The log file is 10GB. How do you watch new error lines appear in real-time?

Ideal Answer: "I would use tail -f error.log. This 'follows' the file and prints new lines to the screen as they are written. If the log is moving too fast to read, I would pipe it into grep to filter only for errors: tail -f error.log | grep 'ERROR'."

Q2: The Disk Space Scenario

Question: Disk is 99% full. How do you find exactly which folder is the culprit?

Ideal Answer: "I would use the du (Disk Usage) command. Specifically, I run du -h --max-depth=1 / | sort -hr.

du -h: Shows sizes in human-readable format (GB, MB).

--max-depth=1: Only shows the top-level folders so I don't get flooded with millions of files.

sort -hr: Sorts the output so the biggest folders appear at the top."

Q3: The Network Scenario

Question: Browser says "Connection Refused" on port 80. How do you check if the server is actually listening?

Ideal Answer: "I would use netstat -tulpn (or ss -tulpn on newer systems).

This lists all TCP/UDP Listening Ports and the Numeric port values.

I would specifically look for a line like 0.0.0.0:80. If it's missing, the web server isn't running or isn't configured to listen on that port."