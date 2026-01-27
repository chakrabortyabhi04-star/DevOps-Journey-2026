# Linux Architecture & Process Management

**Date:** January 28, 2026

## 1. Core Architecture
* **Kernel:** The core that manages hardware (CPU, RAM). It creates the "environment" for apps to run.
* **User Space:** Where applications run. They interact with the Kernel via **System Calls**.
* **Shell:** The interface (like Bash) that lets humans talk to the Kernel.

## 2. Process Lifecycle
Every process has a **PID** (Process ID).
* **Running:** [Describe what this means]
* **Sleeping:** [Why would a process sleep?]
* **Zombie:** A dead process waiting for its parent to read its exit status.
* **Orphan:** A process whose parent died; usually adopted by init/systemd.

## 3. Systemd (The Init System)
* **Role:** The first process (PID 1). It bootstraps the User Space and manages system services (like Nginx, Docker).
* **Why it matters:** It handles dependencies (e.g., "Start Network *before* starting Web Server") and restarts crashed services automatically.

## 4. Top 5 Survival Commands
1.  `top` / `htop`: [What does this show?]
2.  `ps aux`: [What does this show?]
3.  `kill`: [Difference between -9 and -15]
4.  `systemctl`: Used to control services (start, stop, enable).
5.  `journalctl`: Used to view logs managed by systemd.

## 5. Key Concept: Load Average
Load average is the number of processes *waiting* for CPU or Disk I/O.
* High Load + Low CPU = [Disk/IO Bottleneck]