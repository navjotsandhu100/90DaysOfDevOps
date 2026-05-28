# Processes

## View all processes

ps aux

## Live monitoring

top

## Find nginx PID

pgrep nginx

## Top CPU processes

ps aux --sort=-%cpu | head

⸻

# Services

## Check nginx service

systemctl status nginx

## Start nginx

sudo systemctl start nginx

## Stop nginx

sudo systemctl stop nginx

## Test nginx config

sudo nginx -t

⸻

# Logs

## View nginx logs

journalctl -u nginx

## Watch logs live

sudo tail -f /var/log/nginx/error.log

## Exit:

CTRL + C

## Search logs

grep -ri "error" /var/log

⸻

# Networking

## Check IP

ip addr or ip a

## Check open ports

ss -tulnp

## Test website locally

curl localhost

## Test connectivity

ping google.com

## Check DNS

dig google.com

⸻

# File & Log Handling

## Find log files

find /var/log -name "*.log"

## Open large logs safely

less logfile.log

## Exit:

q

⸻

# Important DevOps Learning

Service
↓
Process
↓
Port
↓
Response

If service stops:

* process dies
* port closes
* website becomes unavailable

⸻

# Real Troubleshooting Flow

1. Check service status
2. Check logs
3. Check listening ports
4. Test localhost
5. Check CPU/memory
6. Verify DNS/network
