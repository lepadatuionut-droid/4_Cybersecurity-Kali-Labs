# Week 3 – User Accounts & Permissions (Kali / Apporto)

This lab focused on Linux user management and permission systems — essential for cybersecurity access control. Tasks included working with `/etc/passwd`, creating/removing users, setting passwords, and modifying permissions using symbolic and numeric `chmod`.  
(Reference: CyberSec Tutorial Week 4 document) [1](https://stulsbuac-my.sharepoint.com/personal/s4418500_lsbu_ac_uk/_layouts/15/Doc.aspx?sourcedoc=%7BD0CC5FE1-7578-462F-9D22-FEAE32F90DD8%7D&file=CyberSec%20Tutorial%20Week%204.docx&action=default&mobileredirect=true)

---

## 1. Understanding /etc/passwd

Using:
cat /etc/passwd

The file shows:

- **root** → administrator account  
- **kali** → normal user  
- Additional system service accounts  
- New local users appear at the bottom  
- User IDs (UIDs) typically begin at **1000** for normal users

This file defines:
- Username  
- UID / GID  
- Home directory  
- Login shell  

---

## 2. User Management (adduser / passwd / deluser)

### Create new user

sudo adduser john
What happens internally:
- `/home/john` folder is created  
- Entry added to `/etc/passwd`  
- Default group created (GID = UID)

### Verify creation

cat /etc/passwd | grep john

### Change user password

sudo passwd john
Password updated successfully.

### Delete user (including home directory)

sudo deluser --remove-home john

### Verify deletion

cat /etc/passwd
User should no longer appear.

---

## 3. File Permissions (ls -l)

Example:

drwxr-xr-x 2 kali kali Desktop
-rw-r--r-- 1 kali kali file.txt

Meaning:
- 1st char: **d** = directory, **-** = file  
- Next 3: owner permissions  
- Next 3: group permissions  
- Last 3: others permissions  

Breakdown:
- **r** = read  
- **w** = write  
- **x** = execute  

Structure:  
`rwx r-x r-x`

---

## 4. chmod – Symbolic and Numeric Permission Changes

### Symbolic

chmod u-r Videos
Removes read permission for user (owner) on the Videos directory.

### Numeric (octal)
Initial permissions: `rwx r-x r-x` = **755**

Meaning:
- 7 = rwx  
- 5 = r-x  
- 5 = r-x  

Example:

chmod 755 file1.txt

Numeric system:
- r = 4  
- w = 2  
- x = 1  

Add them to compute permission value.

---

## 5. Security Relevance in Cybersecurity

- Linux enforces **least privilege** via users, groups, UIDs, GIDs.  
- Permissions prevent unauthorized access to sensitive directories (`/etc`, `/var/log`, `/usr/bin`).  
- Account lifecycle management (adduser → passwd → deluser) is foundational to security operations.  
- Incorrect permissions can expose credentials, configs, and logs.  
- Numeric chmod and symbolic chmod are used constantly during hardening and incident response.

---

## 6. Evidence

- Full screenshots document:  
  `docs/Week_3_LAB.docx`

- Individual screenshots placed under:  
  `screenshots/`



---
