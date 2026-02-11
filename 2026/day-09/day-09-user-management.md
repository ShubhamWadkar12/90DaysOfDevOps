# Day 09 – User and Group Management

## Users & Groups Created

### Users
- tokyo
- berlin
- professor
- nairobi

### Groups
- developers
- admins
- project-team

---

## Task 1: Create Users

Commands used:
useradd -m tokyo  
passwd tokyo  

useradd -m berlin  
passwd berlin  

useradd -m professor  
passwd professor  

Verify users:
cat /etc/passwd | grep -E "tokyo|berlin|professor"  
ls /home  

---

## Task 2: Create Groups

Commands used:
groupadd developers  
groupadd admins  

Verify groups:
cat /etc/group | grep -E "developers|admins"  

---

## Task 3: Assign Users to Groups

Assignments:
- tokyo → developers
- berlin → developers, admins
- professor → admins

Commands used:
usermod -aG developers tokyo  
usermod -aG developers,admins berlin  
usermod -aG admins professor  

Verify group membership:
groups tokyo  
groups berlin  
groups professor  

---

## Task 4: Shared Directory (developers)

Directory:
- /opt/dev-project

Commands used:
mkdir /opt/dev-project  
chgrp developers /opt/dev-project  
chmod 775 /opt/dev-project  

Verify permissions:
ls -ld /opt/dev-project  

Test file creation:
sudo -u tokyo touch /opt/dev-project/tokyo.txt  
sudo -u berlin touch /opt/dev-project/berlin.txt  

---

## Task 5: Team Workspace

Create user:
useradd -m nairobi  
passwd nairobi  

Create group:
groupadd project-team  

Add users to group:
usermod -aG project-team nairobi  
usermod -aG project-team tokyo  

Create directory:
mkdir /opt/team-workspace  
chgrp project-team /opt/team-workspace  
chmod 775 /opt/team-workspace  

Verify:
ls -ld /opt/team-workspace  

Test:
sudo -u nairobi touch /opt/team-workspace/nairobi.txt  

---

## Directories Created

- /opt/dev-project → group: developers, permission: 775
- /opt/team-workspace → group: project-team, permission: 775

---

## Commands Used

useradd  
passwd  
groupadd  
usermod  
groups  
mkdir  
chgrp  
chmod  
ls  
cat  
sudo -u  

---

## What I Learned

1. Users need groups to share access.
2. Group permissions control shared folders.
3. Permission problems are solved by checking group and chmod.

---

## Troubleshooting

Permission denied?
- Use sudo

User cannot access directory?
- Check group: groups username
- Check permissions: ls -ld /path
