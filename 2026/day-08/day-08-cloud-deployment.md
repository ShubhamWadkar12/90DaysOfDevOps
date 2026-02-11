# Day 08 – Cloud Deployment (Nginx)

## Goal
Deploy a real web server on cloud and access it from browser.

---

## Part 1: Launch Server & SSH

### Step 1: Create Cloud Instance
- Create EC2 (AWS) or VM (Utho)
- OS: Ubuntu
- Open port 22 (SSH)
- Open port 80 (HTTP)

---

### Step 2: Connect via SSH

AWS:
ssh -i your-key.pem ubuntu@<server-ip>

Utho:
ssh root@<server-ip>

Check:
whoami

---

## Part 2: Install Nginx

### Step 1: Update System
apt update -y

### Step 2: Install Nginx
apt install nginx -y

### Step 3: Check Nginx
systemctl status nginx

---

## Part 3: Open Web Access

- Make sure port 80 is allowed in security group
- Open browser

http://<server-ip>

Result:
- Nginx welcome page opens ✅

(Screenshot taken)

---

## Part 4: Nginx Logs

### Step 1: View Logs
cat /var/log/nginx/access.log

---

### Step 2: Save Logs to File
cat /var/log/nginx/access.log > nginx-logs.txt

Check:
ls
cat nginx-logs.txt

---

### Step 3: Download Logs to Local Machine

AWS:
scp -i your-key.pem ubuntu@<server-ip>:~/nginx-logs.txt .

Utho:
scp root@<server-ip>:~/nginx-logs.txt .

---

## Files Created
- nginx-logs.txt

---

## Commands Used

ssh  
apt update  
apt install nginx  
systemctl status nginx  
cat  
scp  

---

## Challenges Faced

- Web page not opening → opened port 80
- SSH error → checked key and username

---

## What I Learned

- How to connect to cloud server
- How to install Nginx
- How web access works (port 80)
- Logs are stored in /var/log
- This is real production work
