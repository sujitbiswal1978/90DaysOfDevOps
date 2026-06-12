# Day 08 – Cloud Server Setup: Docker, Nginx & Web Deployment

## 90-day Devops Learning plan

## Objective

The goal of this exercise was to launch an Amazon Linux EC2 instance, connect to it using SSH, install Docker and Nginx, configure web access, extract logs, and verify that the web server was accessible from the internet.

---

# Cloud Environment

## Cloud Provider

AWS EC2

## Operating System

Amazon Linux 2023

## Instance Type

t2.micro

---

# Step 1: Launch EC2 Instance

### Configuration

- Created an EC2 instance using Amazon Linux 2023.
- Selected t2.micro instance type.
- Created and downloaded a key pair for SSH access.

### Security Group Rules

| Type | Port | Purpose |
|--------|--------|--------|
| SSH | 22 | Remote access |
| HTTP | 80 | Web access |

### Screenshot

![EC2 Instance](./image/EC2%20Instance.png)

### What I Learned

Security Groups act as virtual firewalls and control incoming traffic to the server.

---

# Step 2: Connect to EC2 Using SSH

## Command

```bash
chmod 400 day08.pem
```

```bash
ssh -i day08.pem ec2-user@PUBLIC_IP
```

### Screenshot

![SSH Connection](./image/SSH%20Connection.png)

### Observation

Successfully connected to the Amazon Linux server using SSH.

### What I Learned

SSH allows secure remote access to Linux servers over the network.

---

# Step 3: Verify Operating System

## Command

```bash
cat /etc/os-release
```

### Screenshot

![OS Details](./image/OS%20Details.png)

### Observation

Confirmed that the server was running Amazon Linux 2023.

### What I Learned

Amazon Linux uses the DNF package manager instead of APT.

---

# Step 4: Update the Server

## Command

```bash
sudo dnf update -y
```

### Screenshot

![System Update](./image/System%20Update.png)

### Observation

Updated installed packages and security updates.

### What I Learned

Updating the system ensures the latest security patches and package versions are installed.

---

# Step 5: Install Docker

## Command

```bash
sudo dnf install docker -y
```

## Start Docker Service

```bash
sudo systemctl enable docker
sudo systemctl start docker
```

## Verify Docker Status

```bash
sudo systemctl status docker
```

### Screenshot

![Docker Status](./image/Docker%20Status.png)

### Observation

Docker service was active and running.

### What I Learned

Docker is a container platform that allows applications to run in isolated environments.

---

# Step 6: Install Nginx

## Command

```bash
sudo dnf install nginx -y
```

## Start Nginx

```bash
sudo systemctl enable nginx
sudo systemctl start nginx
```

## Verify Nginx

```bash
systemctl status nginx
```

### Screenshot

![Nginx Status](./image/Nginx%20Status.png)

### Observation

Nginx service was active and running.

### What I Learned

Nginx is a web server used to serve websites and applications.

---

# Step 7: Verify Nginx Locally

## Command

```bash
curl localhost
```

### Observation

The Nginx HTML page was returned successfully.

### What I Learned

This confirms that Nginx is running correctly on the server.

---

# Step 8: Access Website from Browser

## URL

```text
http://PUBLIC_IP
```

### Screenshot

![Nginx Webpage](./image/Nginx%20Webpage.png)

### Observation

The Nginx welcome page was accessible from the internet.

### What I Learned

Opening Port 80 in the Security Group allows external users to access the web server.

---

# Step 9: Review Nginx Logs

## Access Logs

```bash
sudo tail -20 /var/log/nginx/access.log
```

## Error Logs

```bash
sudo tail -20 /var/log/nginx/error.log
```



### Observation

The logs showed incoming requests and server activity.

### What I Learned

Logs are one of the most important resources for troubleshooting applications and services.

---

# Step 10: Save Logs to a File

## Command

```bash
cat /var/log/nginx/access.log > nginx-logs.txt
```

## Verify

```bash
cat nginx-logs.txt
```

### Observation

Successfully saved Nginx access logs into a separate file.

---

# Step 11: Download Log File

## Command

```bash
scp -i Server-01.pem ec2-user@ec2-35-154-130-155:~/nginx-logs.txt D:\DevOps-all-resources\90DaysOfDevOps\2026\day-08
```
**Or we can tranfer file from WINSCP for tranfering linux to windows**
![WINSCP](<image/WinSCP .png>)

### Observation

Downloaded the log file from the EC2 instance to the local machine.

### What I Learned

SCP can securely transfer files between local systems and remote servers.

---

# Challenges Faced

### Challenge 1

Nginx webpage was not accessible from the browser.

### Solution

Verified that Port 80 was allowed in the EC2 Security Group.

---

### Challenge 2

Unable to connect using SSH initially.

### Solution

Verified key permissions using:

```bash
chmod 400 day08.pem
```

and used the correct username:

```bash
ec2-user
```

---

# Key Takeaways

- Learned how to launch and manage an EC2 instance.
- Learned how to connect to a remote server using SSH.
- Installed and managed Docker services.
- Installed and configured Nginx.
- Learned the importance of Security Groups.
- Practiced log analysis using Nginx logs.
- Learned how to transfer files using SCP.

---

# Conclusion

Successfully launched an Amazon Linux EC2 instance, connected using SSH, installed Docker and Nginx, configured web access, reviewed logs, and verified that the web server was accessible from the internet. This exercise provided hands-on experience with real cloud infrastructure and server management tasks.
