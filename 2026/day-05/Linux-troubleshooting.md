# Linux Troubleshooting Runbook

## Target Service

Service: nginx

Purpose: Web server running on port 80.

⸻

# Environment Information

## System Information

uname -a

Observed:

* Amazon Linux EC2 instance
* Linux kernel information displayed

cat /etc/os-release

Observed:

* Amazon Linux distribution confirmed

⸻

## Filesystem Sanity Check

mkdir -p /tmp/runbook-demo
cp /etc/hosts /tmp/runbook-demo/hosts-copy
ls -l /tmp/runbook-demo

Observed:

* Test directory created successfully
* hosts file copied successfully
* Permissions and ownership verified

⸻

## CPU & Memory Snapshot

uptime

Observed:

* Uptime approximately 1 day
* Load average: 0.00

Interpretation:

* No CPU pressure detected.

free -h

Observed:

* Total RAM: ~916 MB
* Available RAM: ~357 MB

Interpretation:

* Memory usage within normal range.

top

Observed:

* No process consuming excessive CPU.

⸻

## Disk & IO Snapshot

df -h

Observed:

* Disk usage approximately 21%

Interpretation:

* No disk space issues.

du -sh /var/log

Observed:

* Log directory size reviewed.

vmstat 1 5

Observed:

* No obvious CPU, memory, or IO bottlenecks.

⸻

## Network Snapshot

ss -tulnp

Observed:

* Port 80 listening for nginx
* Port 22 listening for SSH

curl -I localhost

Observed:

* HTTP/1.1 200 OK

Interpretation:

* Web service responding successfully.

⸻

## Logs Reviewed

journalctl -u nginx -n 50

Observed:

* Nginx startup messages present
* No critical errors detected

sudo tail -n 50 /var/log/nginx/error.log

Observed:

* Nginx worker processes started successfully
* No recent errors found

⸻

## Quick Findings

* Nginx service running normally
* Website accessible locally
* Port 80 open and listening
* CPU healthy
* Memory healthy
* Disk healthy
* No major log errors observed

⸻

If This Worsens

1. Verify nginx configuration using:

sudo nginx -t

2. Increase log review and monitor live logs:

sudo tail -f /var/log/nginx/error.log

3. Investigate process and resource usage:

top
ps aux --sort=-%cpu | head
ps aux --sort=-%mem | head

4. Restart nginx if required:

sudo systemctl restart nginx

5. Escalate with collected logs and system metrics if issue persists
