# Day 04 – Linux Practice: Processes and Services

### 90-day Devops Learning plan

# Linux Practice – Processes and Services

## Process Check 1

Command:

```
ps aux | head
```

Purpose:
Shows running processes on the system.

---

## Process Check 2

Command:

```bash
top
```

Purpose:
Monitors CPU, memory, and running processes in real time.

---

## Service Check 1

Command:

```bash
systemctl status cron
```

Observation:
The cron service is active and running.

---

## Service Check 2

Command:

```bash
systemctl list-units --type=service
```

Purpose:
Displays active services running on the system.

---

## Log Check 1

Command:

```bash
journalctl -u cron -n 20
```

Purpose:
Shows recent logs for the cron service.

---

## Log Check 2


Command:

```bash
journalctl -n 20
```

Purpose:
Displays recent system logs.

---

## Mini Troubleshooting Flow

Issue:
Wanted to verify whether the cron service was running correctly.

Steps:
1. Checked service status using `systemctl status cron`
2. Reviewed logs using `journalctl -u cron -n 20`
3. Verified that the service was active

Result:
The cron service was running successfully without any issues.

---

## What I Learned

Today I practiced Linux process, service, and log management commands. I learned how to inspect running processes, check service status, and review logs to troubleshoot Linux systems more effectively.