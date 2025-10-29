# 🧪 Lab 1: Basic Linux Commands & Navigation

**Goal:** Learn how to navigate your Linux system, manage files and directories, and check basic system information.  
**Tools:** Linux Terminal (Ubuntu, Kali, or any Linux distribution)

---

## 🧠 Learning Objectives
By the end of this lab, you should be able to:
- Navigate the filesystem using terminal commands
- Create, view, edit, and rename files
- Understand file and folder structures
- Check disk usage and system uptime
- Gain confidence in basic Linux command-line operations

---

## ⚙️ Prerequisites
- A Linux system (Ubuntu, Kali, Parrot OS, etc.)
- Terminal access (`Ctrl + Alt + T`)
- Basic understanding of command-line syntax

---

## 🧩 Step-by-Step Practical Guide

---

### Step 1 — Open the Terminal
Open the terminal (`Ctrl + Alt + T`).  
You should see something like:
daniel@ubuntu:~$

yaml
Copy code
- `daniel` → your username  
- `ubuntu` → computer name  
- `~` → home directory  

This is your **command prompt**, where you type commands.

---

### Step 2 — Check Your Current Directory
Command:
```bash
pwd
Meaning: Print Working Directory — shows your current location.

Example Output:

arduino
Copy code
/home/daniel
Step 3 — List Files and Folders
Command:

bash
Copy code
ls -lah
Explanation:

ls → list files/folders

-l → long format (detailed info)

-a → include hidden files

-h → human-readable sizes

Example Output:

css
Copy code
drwxr-xr-x 3 daniel daniel 4096 Oct 29  Documents
drwxr-xr-x 2 daniel daniel 4096 Oct 29  Downloads
-rw-r--r-- 1 daniel daniel  220 Oct 29  .bash_logout
-rw-r--r-- 1 daniel daniel 3771 Oct 29  .bashrc
-rw-r--r-- 1 daniel daniel  807 Oct 29  .profile
Step 4 — Create a New Directory
Command:

bash
Copy code
mkdir mylab
ls
Meaning:

mkdir → make a directory called mylab

ls → check the folder exists

Expected Output:

nginx
Copy code
Documents  Downloads  mylab
Step 5 — Move Into the Folder
Command:

bash
Copy code
cd mylab
pwd
cd → change directory

pwd → confirm you’re inside mylab

Expected Output:

arduino
Copy code
/home/daniel/mylab
Step 6 — Create a New File
Command:

bash
Copy code
touch info.txt
ls -l
touch → creates an empty file called info.txt

Expected Output:

css
Copy code
-rw-r--r-- 1 daniel daniel 0 Oct 29 12:00 info.txt
Step 7 — Write Text into the File
Command:

bash
Copy code
echo "Linux Essentials Lab 1" > info.txt
cat info.txt
echo → outputs text

> → redirects text into a file

cat → displays file contents

Expected Output:

nginx
Copy code
Linux Essentials Lab 1
Step 8 — Append Text to the File
Command:

bash
Copy code
echo "Practice navigating directories and files" >> info.txt
cat info.txt
>> → appends text without overwriting

Expected Output:

nginx
Copy code
Linux Essentials Lab 1
Practice navigating directories and files
Step 9 — Rename the File
Command:

bash
Copy code
mv info.txt lab1.txt
ls
mv → moves or renames a file

Expected Output:

Copy code
lab1.txt
Step 10 — Copy the File
Command:

bash
Copy code
cp lab1.txt lab1_backup.txt
ls
cp → copies the file

Expected Output:

Copy code
lab1.txt  lab1_backup.txt
Step 11 — Check Disk Space
Command:

bash
Copy code
df -h
Shows disk usage in human-readable format

Example Output:

bash
Copy code
Filesystem      Size  Used Avail Use% Mounted on
/dev/sda1        50G   15G   32G  32% /
tmpfs           2.0G  1.2M  2.0G   1% /run
Step 12 — Check System Uptime
Command:

bash
Copy code
uptime
Example Output:

bash
Copy code
10:45:32 up 3 hours, 2 users, load average: 0.20, 0.25, 0.30
Step 13 — Remove Files and Folders (Cleanup)
Command:

bash
Copy code
rm lab1_backup.txt
cd ..
rm -r mylab
rm → removes files

rm -r → recursively removes folders

✅ Summary
In this lab, you learned:

Navigate directories: pwd, cd, ls

Create, read, write, append, rename, and copy files: touch, echo, cat, mv, cp

Check system info: df -h, uptime

Remove files/folders: rm, rm -r

📸 Optional Exercises
Create directories: projects, notes, scripts

Inside notes, create a file called day1.txt

Write: Learning Linux is fun!

Display contents with cat

Rename day1.txt → introduction.txt

Copy introduction.txt → intro_backup.txt

Practice these steps until you can do them without looking at instructions.
