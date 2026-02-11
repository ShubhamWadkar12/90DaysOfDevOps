#### Environment Basics

- uname -a → Check kernel version and architecture
- cat /etc/os-release → Check OS distribution and version

#### Filesystem Sanity
- mkdir /tmp/runbook-demo → Create temporary directory
- cp /etc/hosts /tmp/runbook-demo/hosts-copy → Test file copy
- ls -l /tmp/runbook-demo → Verify file creation

#### Snapshot: CPU & Memory
- top → Monitor CPU and memory usage in real time
- free -h → Check available and used memory

#### Snapshot: Disk & IO
- df -h → Check disk space usage
- du -sh /var/log → Check size of log directory

#### Snapshot: Network
- ss -tulnp | grep ssh → Verify SSH is listening on port 22
- curl -I http://localhost → Check basic network connectivity

#### Logs Reviewed
- journalctl -u ssh -n 50 → Review recent SSH logs
- tail -n 50 /var/log/auth.log → Review authentication logs
