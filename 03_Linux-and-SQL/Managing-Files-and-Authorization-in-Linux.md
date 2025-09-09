# Managing Files and Authorization in Linux  
*Google Cybersecurity Certificate – Course 03 - Tools of Trade - Linux and SQL*  
*Portfolio Activity – Linux File Management & Permissions*  

---

## 🎯 Lab Summary  
This combined lab focused on two key areas of Linux system administration:  

1. **File and directory management** – creating, removing, moving, and editing files in a Linux environment.  
2. **Authorization and permissions management** – checking and modifying file and directory permissions to ensure proper access control.  

The following tasks were performed:  
- Create and remove directories  
- Move and delete files  
- Create and edit files using `nano`  
- Check file and directory permissions with `ls -l`  
- Identify hidden files  
- Modify file permissions with `chmod`  
- Restrict directory access to authorized users only  

These exercises reinforced practical **Linux file management** and **permission handling skills**, both essential for secure system operations.  

---

## ⚙️ Steps and Commands  

### 1️⃣ Create a new directory  
Commands executed:  
```bash
mkdir logs
ls
```  
- Created a new directory `logs` under `/home/analyst`.  
- Verified its presence with `ls`.  

📸
![Create new dir](../assets/activity-03-03/act-01/img-1.png)

---

### 2️⃣ Remove a directory  
Commands executed:  
```bash
rmdir temp
ls
```  
- Removed the `temp` directory.  
- Verified it no longer appears in the list.  

📸
![Remove dir](../assets/activity-03-03/act-01/img-2.png)

---

### 3️⃣ Move a file  
Commands executed:  
```bash
mv Q3patches.txt /home/analyst/reports/
ls /home/analyst/reports/
```  
- Moved `Q3patches.txt` from `notes` to `reports`.  
- Confirmed the file now exists in the `reports` directory.  

📸
![Move file](../assets/activity-03-03/act-01/img-3.png)

---

### 4️⃣ Remove a file  
Commands executed:  
```bash
rm tempnotes.txt
ls
```  
- Deleted the file `tempnotes.txt` from `notes`.  
- Verified that the file was removed.  

📸
![Remove file](../assets/activity-03-03/act-01/img-4.png)

---

### 5️⃣ Create a new file  
Commands executed:  
```bash
touch tasks.txt
ls
```  
- Created an empty file `tasks.txt` in the `notes` directory.  

📸
![Create empty .txt file](../assets/activity-03-03/act-01/img-5.png)

---

### 6️⃣ Edit a file  
Commands executed:  
```bash
nano tasks.txt
```  
- Edited `tasks.txt` and added task details:  
  ```
  Completed tasks
  1. Managed file structure in /home/analyst
  ```  
- Saved and exited.  

📸
![Edidt file with nano](../assets/activity-03-03/act-01/img-6.png)
📸
![Display file content](../assets/activity-03-03/act-01/img-7.png)

---

### 7️⃣ Check file and directoryy permissionsdetails  
Commands executed:  
```bash
cd projects
ls -l
ls -la
```  
- Listed files with their permissions.  
- Confirmed the group owner: `research_team`.  
- Detected a hidden file: `.project_x.txt`.  

📸
![Check permissions details](../assets/activity-03-03/act-02/img-1.png)  

📸
![Hidden file](../assets/activity-03-03/act-02/img-2.png)

---

### 8️⃣ Change file permissions  
Commands executed:  
```bash
ls -la
chmod o-w project_k.txt
chmod g-r project_m.txt
ls -la
```  
- Found that `project_k.txt` allowed write access for *others* → fixed.  
- Restricted `project_m.txt` so only the owner has full access.  

📸
![Change file permission 1](../assets/activity-03-03/act-02/img-3.png)

📸
![Changes file permission 2](../assets/activity-03-03/act-02/img-4.png)

---

### 9️⃣ Change file permissions on a hidden file  
Commands executed:  
```bash
ls -la
chmod u-w,g-w,+r project_x.txt
ls -la
```  
- Adjusted `.project_x.txt` so it cannot be written to, but remains readable.  

📸
![Change perms on hidden file](../assets/activity-03-03/act-02/img-5.png)

---

### 🔟 Change directory permissions  
Commands executed:  
```bash
ls -la
chmod g-x drafts
ls -la
```  
- Removed group execute permission from `drafts`.  
- Ensured only the user `researcher2` has access to the directory contents.  

📸
![Remove group permisions](../assets/activity-03-03/act-02/img-6.png)

📸
![Ensure access to file](../assets/activity-03-03/act-02/img-7.png)

---

## 🧠 Reflections / Notes  
- Practiced managing Linux file structures with `mkdir`, `rmdir`, `mv`, `rm`, and `touch`.  
- Used `nano` to edit files directly in the terminal.  
- Strengthened understanding of **Linux file permissions** using `ls -l`, `ls -la` and `chmod`.  
- Learned to secure files and directories by restricting unauthorized access.  
- Reinforced key sysadmin practices in **authorization management** and **principle of least privilege**.  

---

## 📚 Key Skills Demonstrated  
- Linux file and directory management  
- File creation and editing with `nano`  
- Understanding of file ownership and permissions (`ls -l`)  
- Permission modification with `chmod`  
- Hidden file detection and restriction (`ls -la`) 
- Directory access control  
- **UNIX terminal workflow and Git documentation practices**  

---

*This extended activity demonstrates the ability to manage files and enforce authorization policies in Linux, applying both system administration and security principles.*  

