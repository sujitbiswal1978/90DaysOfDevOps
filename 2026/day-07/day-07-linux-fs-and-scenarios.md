# Day 07 – Linux File System Hierarchy & Scenario-Based Practice

## 90-day Devops Learning plan

## Objective

The goal of this exercise is to understand the Linux File System Hierarchy and practice solving common troubleshooting scenarios that a DevOps Engineer may encounter in real-world environments.

---

# Part 1: Linux File System Hierarchy

## 1. Root Directory (/)

### Purpose

The root directory (/) is the top-level directory in Linux. Every file and directory starts from this location.

### Example

```bash
ls -l /
```

Common directories:

- home
- etc
- var

### When I Would Use This

I would use this when navigating the Linux file system and locating important system directories.

---

## 2. Home Directory (/home)

### Purpose

The /home directory contains personal directories and files for normal users.

### Example

```bash
ls -l /home
```

Common folders:

- sujit
- ubuntu

### When I Would Use This

I would use this when accessing user files and personal data.

---

## 3. Root User Directory (/root)

### Purpose

The /root directory is the home directory of the root user.

### Example

```bash
ls -l /root
```

Common files:

- scripts
- configuration files

### When I Would Use This

I would use this when working as a Linux administrator with root privileges.

---

## 4. Configuration Directory (/etc)

### Purpose

The /etc directory stores system configuration files.

### Example

```bash
ls -l /etc | head
```

Common files:

- hosts
- hostname
- passwd

### When I Would Use This

I would use this when modifying system configurations or troubleshooting configuration issues.

---

## 5. Log Directory (/var/log)

### Purpose

The /var/log directory stores system and application log files.

### Example

```bash
ls -l /var/log | head
```

Common files:

- syslog
- auth.log

### When I Would Use This

I would use this when investigating system problems and reviewing logs.

---

## 6. Temporary Directory (/tmp)

### Purpose

The /tmp directory stores temporary files created by users and applications.

### Example

```bash
ls -l /tmp
```

Common contents:

- temporary folders
- temporary files

### When I Would Use This

I would use this for testing, temporary storage, and troubleshooting activities.

---

## 7. Binary Directory (/bin)

### Purpose

The /bin directory contains essential Linux commands.

### Example

```bash
ls -l /bin | head
```

Common commands:

- ls
- cp
- mv

### When I Would Use This

I would use this when executing basic Linux commands required for system operation.

---

## 8. User Binary Directory (/usr/bin)

### Purpose

The /usr/bin directory contains user-level command binaries and applications.

### Example

```bash
ls -l /usr/bin | head
```

Common commands:

- grep
- find
- vim

### When I Would Use This

I would use this when running user applications and Linux utilities.

---

## 9. Optional Software Directory (/opt)

### Purpose

The /opt directory stores optional and third-party applications.

### Example

```bash
ls -l /opt
```

Common applications:

- Tomcat
- Custom software

### When I Would Use This

I would use this when installing or managing third-party applications.

---

# Hands-On Practice

## Find Largest Log Files

### Command

```bash
du -sh /var/log/* 2>/dev/null | sort -h | tail -5
```

### Observation

This command helps identify the largest log files that may consume disk space.

---

## View Hostname

### Command

```bash
cat /etc/hostname
```

### Observation

Displayed the hostname of the system.

---

## Check Home Directory

### Command

```bash
ls -la ~
```

### Observation

Displayed files and directories available in the current user's home directory.

---

# Part 2: Scenario-Based Practice

## Scenario 1: Service Not Starting

### Problem

A service called "myapp" failed to start after a server reboot.

### Step 1

#### Command

```bash
systemctl status myapp
```

#### Why

To check whether the service is active, failed, or stopped.

---

### Step 2

#### Command

```bash
journalctl -u myapp -n 50
```

#### Why

To review recent logs and identify the reason for failure.

---

### Step 3

#### Command

```bash
systemctl is-enabled myapp
```

#### Why

To verify whether the service is configured to start automatically during boot.

---

### Step 4

#### Command

```bash
systemctl list-units --type=service
```

#### Why

To verify that the service exists on the system.

---

### What I Learned

Always check the service status first, then review logs before making changes.

---

# Scenario 2: High CPU Usage

### Problem

The application server is responding slowly.

### Step 1

#### Command

```bash
top
```

#### Why

To monitor CPU usage in real time.

---

### Step 2

#### Command

```bash
ps aux --sort=-%cpu | head -10
```

#### Why

To identify processes consuming the highest CPU resources.

---

### Step 3

#### Command

```bash
pgrep process_name
```

#### Why

To find the Process ID (PID).

---

### Step 4

#### Command

```bash
ps -p PID -o pid,ppid,cmd,%cpu,%mem
```

#### Why

To view detailed information about the process.

---

### What I Learned

CPU troubleshooting starts by identifying the process consuming excessive resources.

---

# Scenario 3: Finding Service Logs

### Problem

A developer wants to view Docker service logs.

### Step 1

#### Command

```bash
systemctl status docker
```

#### Why

To verify whether the Docker service is running.

---

### Step 2

#### Command

```bash
journalctl -u docker -n 50
```

#### Why

To display the latest Docker service logs.

---

### Step 3

#### Command

```bash
journalctl -u docker -f
```

#### Why

To monitor Docker logs in real time.

---

### What I Learned

systemd-managed service logs can be accessed using journalctl.

---

# Scenario 4: File Permission Issue

### Problem

A script named backup.sh shows "Permission denied" when executed.

### Step 1

#### Command

```bash
ls -l backup.sh
```

#### Why

To check current file permissions.

---

### Step 2

#### Command

```bash
chmod +x backup.sh
```

#### Why

To add execute permission to the script.

---

### Step 3

#### Command

```bash
ls -l backup.sh
```

#### Why

To verify that execute permission has been added.

---

### Step 4

#### Command

```bash
./backup.sh
```

#### Why

To test whether the script executes successfully.

---

### What I Learned

Linux scripts require execute permissions before they can be run.

---

# Key Takeaways

- Learned the purpose of important Linux directories.
- Understood where configuration files, logs, binaries, and user files are stored.
- Practiced troubleshooting service failures.
- Learned how to investigate high CPU usage.
- Learned how to locate service logs using journalctl.
- Understood how Linux file permissions affect script execution.

---

# What I Learned

Today I learned about the Linux File System Hierarchy and how different directories serve different purposes. I also practiced real-world troubleshooting scenarios involving services, CPU utilization, logs, and file permissions. These concepts are important for Linux Administration, DevOps, and Cloud Engineering roles.

