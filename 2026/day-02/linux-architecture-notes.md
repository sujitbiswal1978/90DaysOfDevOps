# Day 02 – Linux Architecture, Processes, and systemd

### **90-day Devops Learning plan**

## Linux Core Components

### Kernel
- The core part of Linux.
- Manages CPU, memory, storage, and hardware devices.

### User Space
- The area where users and applications interact with the system.
- Applications run in user space.

### systemd
- The first process started during system boot.
- Manages services and system processes.

---

## Processes

- A process is a running program.
- Every process has a unique Process ID (PID).
- Linux uses processes to run applications and services.

### Process States

- Running (R): Process is actively using CPU.
- Sleeping (S): Process is waiting for an event or resource.
- Stopped (T): Process execution has been paused.
- Zombie (Z): Process has finished execution but still exists in the process table.

---

---

## Why systemd Matters

- Starts services during system boot.
- Stops and restarts services when needed.
- Helps manage system logs and background services.

---
## 5 Useful Linux Commands
> `ps aux` – View running processes.

> `top` – Monitor system resources and processes.

> `systemctl status <service>` – Check service status.

> `journalctl` – View system logs.

> `ps -p 1` – Check the init process (systemd).

---

## What I Learned

Today I learned how Linux is structured, how processes are managed, and how systemd controls services. Understanding these concepts will help me troubleshoot Linux systems more effectively in the future.

### **Thank You...**