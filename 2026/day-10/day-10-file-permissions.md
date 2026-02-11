# Day 10 – File Permissions and File Operations

## Task 1: Create Files

Create empty file:
touch devops.txt

Create file with content:
echo "My DevOps notes" > notes.txt

Create script using vim:
vim script.sh
(write inside)
echo "Hello DevOps"

Check permissions:
ls -l

---

## Task 2: Read Files

Read file:
cat notes.txt

Open script in read-only mode:
vim -R script.sh

First 5 lines of passwd:
head -n 5 /etc/passwd

Last 5 lines of passwd:
tail -n 5 /etc/passwd

---

## Task 3: Understand Permissions

Permission format:
rwxrwxrwx  
owner  group  others

Meaning:
r = read  
w = write  
x = execute  

Check file permissions:
ls -l devops.txt notes.txt script.sh

Answer:
- devops.txt → read/write
- notes.txt → read/write
- script.sh → read/write (not executable)

---

## Task 4: Change Permissions

Make script executable:
chmod +x script.sh

Run script:
./script.sh

Make devops.txt read-only:
chmod a-w devops.txt

Set notes.txt to 640:
chmod 640 notes.txt

Create directory:
mkdir project
chmod 755 project

Check after every change:
ls -l

---

## Task 5: Test Permissions

Write to read-only file:
echo "test" >> devops.txt

Result:
Permission denied

Run file without execute permission:
chmod -x script.sh
./script.sh

Result:
Permission denied

---

## Files Created

- devops.txt
- notes.txt
- script.sh
- project/

---

## Commands Used

touch  
echo  
cat  
vim  
head  
tail  
chmod  
ls  
mkdir  

---

## What I Learned

- Files need permission to work
- Execute permission is needed to run scripts
- chmod is used to fix permission problems
