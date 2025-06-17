# Day 3 – Boot Process, Systemd & Service Management

## 🚀 Boot Sequence Overview

The Linux boot process happens in this order:

1. **BIOS/UEFI** – Hardware checks & boot device loading
2. **GRUB** – Bootloader that lets you select the OS/kernel
3. **Kernel** – Loads drivers & mounts root filesystem
4. **init/systemd** – Starts system processes and services

---

## 🧠 Key Commands

| Command                      | Description                                |
|------------------------------|--------------------------------------------|
| `uname -r`                   | Shows kernel version                       |
| `systemctl`                  | Controls services & targets                |
| `systemctl status`           | View service status                        |
| `systemctl enable <service>` | Start service at boot                      |
| `systemctl disable <service>`| Prevent service from auto-starting         |
| `systemctl start <service>`  | Start service now                          |
| `systemctl stop <service>`   | Stop service now                           |
| `systemctl restart <svc>`    | Restart a service                          |
| `journalctl -b`              | View boot log                              |
| `systemctl list-units`       | Show active services                       |

---

## 🔧 Practice Lab

```bash
# View your running kernel
uname -r

# See all active services
systemctl list-units --type=service

# Check status of a service (e.g. ssh)
systemctl status sshd

# Start and enable a service
sudo systemctl start sshd
sudo systemctl enable sshd

# Disable and stop a service
sudo systemctl stop apache2
sudo systemctl disable apache2

# View logs from last boot
journalctl -b

