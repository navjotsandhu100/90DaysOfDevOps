# Linux Architecture Notes

## Kernel
The kernel is the core of Linux. It manages CPU, memory, hardware, processes, filesystems, and networking. Applications communicate with hardware through the kernel using system calls.

## User Space
User space is where applications and user programs run, such as bash, nginx, Chrome, and system tools. Applications cannot directly access hardware and must request services from the kernel.

## systemd
systemd is the init system used in most modern Linux distributions. It starts and manages services during boot, handles service restarts, manages dependencies, and stores logs using journalctl.

Common commands:
- systemctl status nginx
- systemctl restart nginx
- journalctl -u nginx

## Processes
A process is a running program with a unique PID (Process ID). Linux creates processes using fork() and exec(). The kernel manages process scheduling and resource usage.

## Process States
- Running (R) → actively using CPU
- Sleeping (S) → waiting for input or resources
- Zombie (Z) → finished process waiting for cleanup
- Stopped (T) → paused process

## Daily Linux Commands
- ps aux → view running processes
- top → monitor CPU and memory usage
- systemctl → manage services
- journalctl → view service logs
- df -h → check disk space

## Why Important for DevOps
Linux is the base OS for most servers and cloud systems. Understanding processes and systemd helps troubleshoot crashed services, high CPU usage, memory issues, and application failures quickly.
