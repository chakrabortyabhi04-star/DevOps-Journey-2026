
# Linux Troubleshooting Runbook: Cron Service
**Date:** February 2, 2026
**Author:** Abhishek Chakraborty
**Target Service:** Cron (Task Scheduler)

## 1. Incident Overview
**Goal:** Verify health of the Cron scheduler and check for failed jobs.

## 2. System Vitals (Snapshot)
| Metric | Command | Result/Observation |
| :--- | :--- | :--- |
| **Uptime/Load** | `uptime` | Load avg:  |
| **Memory** | `free -h` | Free RAM:  |
| **Disk Space** | `df -h /` | Disk Usage:  |
               total        used        free      shared  buff/cache   available
Mem:           6.7Gi       1.4Gi       3.0Gi       8.0Mi       2.5Gi       5.3Gi
Swap:          2.0Gi          0B       2.0Gi


## 3. Service Health Check
* **Process Status:**
    * Command: `ps aux | grep cron`
    * PID Found: `178`
    * Status: Process is running as root.

* **Network Ports:**
    * Command: `ss -tuln`
    * Observation: Cron does not listen on public ports (Normal).

## 4. Log Analysis
**Command:** `journalctl -u cron --since "1 hour ago" | tail -n 5`
**Recent Activity:**
                 [::]:*Failed to parse timestamp: i hour ago
wq

wq
wq

