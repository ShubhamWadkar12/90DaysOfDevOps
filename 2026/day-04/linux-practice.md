- ps aux → Check all running processes
- top → Check running processes in real time

- systemctl status ssh → Check service status
- systemctl list-units --type=service  → List all running services

- journalctl -u ssh → View logs for a specific service
- journalctl -u ssh -n 20 → View recent logs only
- journalctl -u ssh -f  → Monitor logs in real time

#### Mini Troubleshooting Flow (Example)
> Problem: SSH not working

##### Check if process exists
``` pgrep sshd ```
##### Check service status
```systemctl status ssh```
##### Restart service if needed
```sudo systemctl restart ssh```
##### Check logs for errors
```journalctl -u ssh -n 20```
##### Verify port listening
```ss -tulnp | grep 22```
