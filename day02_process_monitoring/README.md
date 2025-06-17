# Day 2 – Process and System Monitoring (Linux+ XK0-005)

## 🧠 Goal
Understand how to view, manage, prioritize, and monitor system processes using core Linux tools.

---

## 🔧 Core Commands

| Command              | What It Does                           |
|----------------------|----------------------------------------|
| `ps aux`             | Snapshot of all running processes      |
| `top` / `htop`       | Real-time monitoring of CPU/memory     |
| `kill`, `killall`    | Terminate specific or named processes  |
| `nice`, `renice`     | Adjust process priority (CPU usage)    |
| `uptime`             | Show system uptime & load average      |
| `free -h`            | RAM usage (human readable)             |
| `df -h`              | Disk usage by filesystem               |
| `journalctl`         | Show system logs                       |
| `systemctl status`   | View service status                    |

---

## 🧪 Practice Lab

```bash
# Monitor real-time system usage
top

# View processes running as any user
ps aux

# Kill a dummy process (replace 1234 with real PID)
kill -9 1234

# View memory and disk space
free -h
df -h

# View system uptime and load
uptime

# View logs
journalctl -xe

# Check service status (e.g. SSH)
systemctl status sshd
