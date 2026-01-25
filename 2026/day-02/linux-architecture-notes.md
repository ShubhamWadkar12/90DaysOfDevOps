Everything in Linux is either File or Directory

- cd -> change directory
- cd /   -> root directory
- cd ..    -> one folder back
- ls -> list things
- man cp   -> manual of cp

- cd /usr/bin + ls         -> list all linux commands
- cd /bin + ls cp   -> to find similar command
- cd sbin       ->    system binaries

## Task : Write 5 popular linux Commands and thier usages
### Create a file or a folder (directory) Make a folder (directory)
- mkdir devops

### Copy / move / remove / rename file or a folder
- cp -r devops devops-judwa/          (- r for copying everything inside folder)        cp SRC DEST
- mv devops new_devops
- rmdir devops

### ip address find
- ipconfig
- ip addr
- ip -d addr (detailed)
- ip a

### ping a website
- ping www.google.com

### Storage / RAM Usage
- df -h

- touch hello.txt     -> creating file
- free -h -> Shows how much RAM (memory) is total, used, and free.
- df -h -> Shows disk size in GB / MB

| Feature   | RAM                     | Disk                        |
| --------- | ----------------------- | --------------------------- |
| Full form | Random Access Memory    | Hard Disk / SSD             |
| Purpose   | Runs programs           | Stores files                |
| Speed     | Very fast ⚡             | Slower                      |
| Data loss | Lost when power off ❌   | Saved even after shutdown ✅ |
| Example   | Chrome, VS Code running | Movies, photos, OS files    |

### ps aux | grep ping 
- ps → Displays running processes
- a → Shows processes of all users
- u → Shows detailed user-oriented information (CPU, memory, user)
- x → Shows processes not attached to a terminal

| **Binary**                  | **System Binary**                     |
| --------------------------- | ------------------------------------- |
| Executable program          | System-level executable               |
| Used for normal operations  | Used for system administration        |
| Normal users                | Mainly root (admin)                   |
| General use                 | Critical for system                   |
| `/bin`, `/usr/bin`          | `/sbin`, `/usr/sbin`                  |
| Can be run by all users     | Mostly restricted                     |
| `ls`, `cp`, `mkdir`, `ping` | `reboot`, `mount`, `fsck`, `shutdown` |
- | (pipe) → Sends output of one command to another command
- grep → Searches/filter text
- ping → The keyword being searched (process name)
