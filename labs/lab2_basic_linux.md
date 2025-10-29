# 🧪 Lab 2: Advanced Linux Commands — File Permissions, Users & Utilities

**Goal:** Learn practical Linux commands for managing file permissions, users, groups, and performing advanced file operations.  
**Tools:** Linux Terminal (Ubuntu, Kali, or any Linux distribution)

---

## 🧠 Learning Objectives
By the end of this lab, you should be able to:
- Understand and modify file permissions using `chmod`, `chown`, and `chgrp`
- Create, modify, and delete users and groups
- Locate files using `find` and `locate`
- Identify file types with the `file` command
- Use `stat` and `ls -l` to inspect file attributes
- Apply advanced practical Linux commands in real scenarios

---

## ⚙️ Prerequisites
- Completion of Lab 1: Basic Linux Commands & Navigation
- Terminal access (`Ctrl + Alt + T`)
- Basic knowledge of file creation, navigation, and text redirection

---

## 🧩 Step-by-Step Practical Guide

### Step 1 — Checking File Permissions
```bash
ls -l
```
**Explanation:** `ls -l` lists all files in the current directory with detailed permissions, ownership, and file size.
- r → read permission
- w → write permission
- x → execute permission
- First character d → directory, - → file

**Expected Output:**
```bash
-rw-r--r-- 1 daniel daniel 123 Oct 29 12:00 lab2.txt
drwxr-xr-x 2 daniel daniel 4096 Oct 29 12:05 projects
```

---


### Step 2 — Changing File Permissions
```bash
chmod 744 lab2.txt
ls -l lab2.txt
```
**Explanation:** chmod 744 lab2.txt sets the owner to read/write/execute, group to read, others to read only.

**Expected Output:**
```bash
-rwxr--r-- 1 daniel daniel 123 Oct 29 12:00 lab2.txt
```

---


### Step 3 — Changing Ownership
```bash
sudo chown root:root lab2.txt
ls -l lab2.txt
```
**Explanation:**
chown root:root lab2.txt changes the owner and group of the file to root.

**Expected Output:**
```bash
-rwxr--r-- 1 root root 123 Oct 29 12:00 lab2.txt
```

---

### Step 4 - Create a New User and Group
```bash
sudo adduser student1
sudo addgroup students
sudo usermod -aG students student1
```
**Explanation:**
- adduser student1 creates a new user
- addgroup students creates a new group
- usermod -aG students student1 adds the user to the group.

**Check user groups:**
```bash
groups student1
```

**Expected Output:**
```bash
-rwxr--r-- 1 root root 123 Oct 29 12:00 lab2.txt
```

---

### Step 5 - Locate Uasge
```bash
locate lab2.txt
```
**Explanation:**
Find all files named lab2.txt on your system.

**Expected Output:**
```bash
/home/daniel/mylab/lab2.txt
/home/daniel/mylab/projects/lab2.txt
```

---


### Step 6 - Limit locate output
```bash
locate lab2.txt | head -5
```
**Explanation:**
Show only the first 5 matches using head.

**Expected Output:**
```bash
/home/daniel/mylab/lab2.txt
/home/daniel/mylab/projects/lab2.txt
```

---

### Step 7 - Use grep with locate
```bash
locate lab2.txt | grep "/home/daniel"
```
**Explanation:**
Filter locate results for files inside /home/daniel.

**Expected Output:**
```bash
/home/daniel/mylab/lab2.txt
/home/daniel/mylab/projects/lab2.txt
```

---
### Step 8 - Find files by name
```bash
find ~/mylab -type f -name "*.txt"
```
**Explanation:**
Search in ~/mylab for .txt files only.

**Expected Output:**
```bash
/home/daniel/mylab/lab2.txt
/home/daniel/mylab/projects/lab2.txt
```

---

### Step 9 - find file using last modify
```bash
find ~/mylab -type f -mtime -7
```
**Explanation:**
find ~/mylab -type f -mtime -7
- -mtime -7 → modified in the last 7 days

**Expected Output:**
```bash
/home/daniel/mylab/lab2.txt
/home/daniel/mylab/projects/lab2.txt
```

---

### Step 10 - Identify File Types
```bash
file lab2.txt
file projects
```
**Explanation:**
file lab2.txt determines the type of a file.

**Expected Output:**
```bash
lab2.txt: ASCII text
projects: directory
```

---

### Step 11 - View File Metadata with stat
```bash
stat lab2.txt
```
**Explanation:**
stat lab2.txt shows detailed metadata like size, permissions, modification time, and inode.

**Expected Output:**
```bash
  File: lab2.txt
  Size: 123        Blocks: 8          IO Block: 4096 regular file
Device: 802h/2050d Inode: 1234567     Links: 1
Access: 2025-10-29 12:00:00.000000000 +0100
Modify: 2025-10-29 12:00:00.000000000 +0100
Change: 2025-10-29 12:01:00.000000000 +0100
 Birth: -
```

---


### Step 12 - Combine Commands with Pipes
```bash
ls -l | grep ".txt"
```
**Explanation:**
ls -l | grep ".txt" lists all files and filters only .txt files using a pipe to grep.

**Expected Output:**
```bash
 -rwxr--r-- 1 root root 123 Oct 29 12:00 lab2.txt
-rw-r--r-- 1 daniel students 45 Oct 29 12:05 notes.txt
```

---

### Step 13 - Advanced Cleanup
```bash
sudo deluser student1
sudo delgroup students
rm lab2.txt
```
**Explanation:**
Remove test users, groups, and files after lab practice.

**Expected Output:**
```bash
  
```

---

## ✅ Summary

**In this lab, you practiced:**

- Inspecting and modifying file permissions: chmod, chown, chgrp
- Creating and managing users and groups: adduser, addgroup, usermod, groups
- Searching files: locate, find
- Checking file types: file
- Viewing file metadata: stat
- Combining commands and filtering output with pipes

## 📸 Optional Exercises
- Create a file with owner-only read/write permissions.
- Add a new user, assign to a group, create a file owned by that user/group.
- Locate all .log files in /var/log.
- Identify types of all files in a directory using file *.
- Pipe ls -l output to grep to display only directories.
- Practice these steps until you can perform them without instructions.

## 🧾 Next Lab

Lab 3: System Monitoring & Process Management
Learn how to monitor processes, CPU/memory usage, and manage running services in Linux.
