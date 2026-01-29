# Day 04: Practical Process & Service Management (Ubuntu Edition)

**Date:** January 29, 2026
**Environment:** Ubuntu 22.04 LTS (WSL)

## 1. Service Inspection (Success)
**Command:** `systemctl status cron`
* **Status:** Active (Running)
* **PID:** 207 cron
* **Memory:**  412.0K (peak: 1.7M)

## 2. Process Checks
**Command:** `top -b -n 1 | head -n 5`
**abhishek@Abhishek:~$ top -b -n 1 | head -n 5
top - 00:01:16 up 52 min,  1 user,  load average: 0.13, 0.04, 0.08
Tasks:  28 total,   1 running,  27 sleeping,   0 stopped,   0 zombie
%Cpu(s):  0.0 us,  1.2 sy,  0.0 ni, 98.8 id,  0.0 wa,  0.0 hi,  0.0 si,  0.0 st
MiB Mem :   6844.2 total,   5933.3 free,    520.4 used,    542.0 buff/cache
MiB Swap:   2048.0 total,   2048.0 free,      0.0 used.   6323.8 avail Mem
abhishek@Abhishek:~$
* **Observation:** The system is running standard Linux daemons.

## 3. Log Investigation
**Command:** `journalctl -u cron -n 5`
-- No entries --
* **Output:** I can now see the actual system logs for the scheduler service.Main PID: 207 (cron)
