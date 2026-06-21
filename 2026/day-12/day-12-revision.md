# Day 12 – Breather & Revision (Days 01–11)

## 90 Days of DevOps Learning Plan

## Objective

The goal of this revision day was to reinforce the Linux fundamentals learned during Days 01–11. Instead of learning new concepts, I reviewed key commands, practiced file operations, checked services, and refreshed user, group, permission, and ownership management concepts.

---

# Task 1: Review Learning Plan

## Review Day 01 Goals

### Observation

I revisited my original DevOps learning plan and evaluated my progress.

### Progress So Far

- Learned basic Linux commands

- Practiced file and directory operations

- Understood process and service management

- Learned user and group administration

- Practiced file permissions and ownership management

### Areas to Improve

- More hands-on Linux troubleshooting
- Faster command-line navigation
- More real-world administration tasks

---

# Task 2: Process & Service Practice

## Check Running Processes

### Command

```bash
ps aux | head
```

### Observation

Displayed currently running processes and system activities.

---

## Check Service Status

### Command

```bash
systemctl status sshd
```

### Observation

Verified that the SSH service is active and running correctly.

---

## Check Service Logs

### Command

```bash
journalctl -u sshd -n 10
```

### Observation

Displayed the latest SSH service log entries.

---

# Task 3: File Skills Revision

## Create File

### Command

```bash
touch revision.txt
```

### Observation

Created a new file for revision practice.

---

## Add Content

### Command

```bash
echo "Day 12 Revision Practice" >> revision.txt
```

### Observation

Appended text to the file.

---

## Change Permissions

### Command

```bash
chmod 644 revision.txt
```

### Observation

Set file permissions to:

```text
-rw-r--r--
```

---

## Change Ownership

### Command

```bash
sudo chown tokyo revision.txt
```

### Observation

Changed the file owner successfully.

---

## Verify

### Command

```bash
ls -l revision.txt
```

### Observation

Verified permission and ownership changes.

---

# Task 4: Command Cheat Sheet Refresh

## Five Commands I Use Most

### 1. List Files

```bash
ls -l
```

Used to view files, permissions, ownership, and timestamps.

---

### 2. Present Working Directory

```bash
pwd
```

Used to identify the current directory.

---

### 3. Change Directory

```bash
cd
```

Used for navigation.

---

### 4. View File Content

```bash
cat
```

Used to quickly read file contents.

---

### 5. Create Directory

```bash
mkdir
```

Used to create project directories.

---

# Task 5: User & Group Revision

## Create Test File

### Command

```bash
touch test-file.txt
```

### Observation

Created a file for ownership testing.

---

## Change Owner

### Command

```bash
sudo chown tokyo test-file.txt
```

### Observation

Changed ownership successfully.

---

## Verify User Information

### Command

```bash
id tokyo
```

### Observation

Displayed user ID, group ID, and associated groups.

---

## Verify Ownership

### Command

```bash
ls -l test-file.txt
```

### Observation

Confirmed that ownership was updated correctly.

---

# Mini Self-Check

## 1. Which 3 Commands Save You the Most Time?

`ls -l`

Provides detailed file information, permissions, and ownership.

`systemctl status`

Quickly checks service health and status.

`cat`

Allows instant viewing of file contents.

---

## 2. How Do You Check If a Service Is Healthy?

### Commands

```bash
systemctl status sshd
```

```bash
ps aux | grep sshd
```

```bash
journalctl -u sshd -n 20
```

### Observation

These commands help verify service status, running processes, and recent logs.

---

## 3. How Do You Safely Change Ownership and Permissions?

### Example

```bash
sudo chown professor:planners project-config.yaml
```

```bash
chmod 640 project-config.yaml
```

### Verify

```bash
ls -l project-config.yaml
```

### Observation

Always verify ownership and permissions after making changes.

---

## 4. What Will I Focus on in the Next 3 Days?

- Linux Administration
- Process Monitoring
- Service Management
- User and Group Management
- Troubleshooting Linux Issues

---

# Key Takeaways

1. Revision helps strengthen previously learned concepts.
2. Linux commands become easier through repeated practice.
3. File permissions and ownership are critical for security.
4. Service monitoring is an important Linux administration skill.
5. Hands-on practice improves confidence and troubleshooting ability.

---

# Conclusion

Today was a revision and reinforcement day. I reviewed everything learned from Days 01–11, including Linux commands, process management, service monitoring, user and group administration, file permissions, and ownership management. This revision helped strengthen my understanding and prepared me for upcoming DevOps topics.
