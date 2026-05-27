# DevOps Linux Must-Have Cheat Sheet

## Navigation & File Management

### pwd
Show current working directory.

### ls -l
List files with permissions and details.

### cd <directory>
Change directory.

### mkdir <name>
Create a new directory.

### rm -rf <name>
Remove files/directories recursively.

### cp source destination
Copy files or directories.

### mv source destination
Move or rename files.

### cat <file>
Display file contents.

### less <file>
View large files page by page.

### tail -f logfile
Monitor logs in real time.

### grep "text" file
Search text inside files.

### find /path -name file
Search for files/directories.

---

## Process Management

### ps aux
View all running processes.

### top
Monitor CPU and memory usage live.

### kill <PID>
Terminate a process using PID.

### pgrep <name>
Find process ID by name.

### nohup command &
Run process in background after logout.

---

## Service Management

### systemctl status nginx
Check service status.

### systemctl restart nginx
Restart service.

### journalctl -u nginx
View service logs.

---

## Networking Commands

### ping google.com
Test network connectivity.

### ip a
View IP addresses and interfaces.

### curl http://example.com
Test APIs and HTTP requests.

## imp http  status codes

200      Success

404      page not found

500      server error

403      forbidden

### dig google.com
Check DNS resolution.

### ss -tulnp
View listening ports and connections.

---

## Disk & Memory

### df -h
Check disk space usage.

### du -sh folder
Check folder size.

### free -h
Check memory usage.

---

## Permissions

### chmod 755 file
Change file permissions.

### chown user:user file
Change file ownership.

---

## System Information

### uname -a
Display Linux kernel/system information.

### uptime
Show system uptime and load average.

---

# Common DevOps Troubleshooting Flow

## Website Down
- systemctl status nginx
- journalctl -u nginx
- ps aux
- curl localhost

## Server Slow
- top
- free -h
- df -h

## Network Issue
- ping
- ip addr
- dig
- ss -tulnp
