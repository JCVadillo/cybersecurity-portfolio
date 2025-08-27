# Installing and Managing Software in Linux with APT  
*Google Cybersecurity Certificate – Course 03: Tools of the Trade: Linux and SQL*  
*(Portfolio Activity – Linux Software Management)*  

---

## 🎯 Lab Summary  
This lab focused on practicing **Linux software management** using the **APT package manager**.  
The following tasks were performed:  

- Confirm that APT is installed  
- Install **Suricata**  
- Verify Suricata installation  
- Uninstall Suricata  
- Install **tcpdump**  
- List installed applications  
- Reinstall Suricata  

The goal was to develop hands-on skills in Linux administration and gain experience with **network security tools**.

---

## ⚙️ Steps and Commands  

### ✅ Confirm that APT is installed  
Command executed:  
```bash
apt
```  
This displays the installed version of APT and its most common commands.  

📸
![Confirm APT installed](../assets/img/confirm-apt-is-installed.png)

---
### 📥 Install Suricata  
Command executed:  
```bash
sudo apt install suricata
```  
This installs Suricata along with required dependencies.  

📸 
![Install Suricata](../assets/img/install-suricata.png)

---

### 🔎 Verify Suricata installation  
Command executed:  
```bash
suricata -h
```  
This confirms Suricata was installed and shows available options.  

📸
![Confirm Suricata is Installed](../assets/img/confirm-suricata-installed.png)

---

### 🗑️ Uninstall Suricata  
Command executed:  
```bash
sudo apt remove suricata
```  
This removes Suricata from the system.  

📸
![Remove Suricata](../assets/img/remove-suricata.png)

---

### 📥 Install tcpdump  
Command executed:  
```bash
sudo apt install tcpdump
```  
This installs the tcpdump packet analyzer.  

📸
![Install tcpdump(../assets/img/install-tcpdump.png)

---

### 📋 List installed applications  
Command executed:  
```bash
apt list --installed
```  
This displays all currently installed applications.  

📸
![List Installed Applications](../assets/img/check-installed-apps.png)

---

### 🔄 Reinstall Suricata  
Command executed:  
```bash
sudo apt install suricata
```  
This reinstalls Suricata to ensure it is available for use.  

📸
![Reinstall Suricata](../assets/img/reinstall-suricata.png)

---

## 🧠 Reflections / Notes
- This Markdown has been created and modify from the Terminal with git and linux commands, including adding the images  
- Practiced managing software lifecycle on Linux (install, verify, remove, reinstall).  
- Learned how to confirm dependencies and verify installations with command-line options.  
- Worked with two essential **network security tools**:  
  - **Suricata**: an intrusion detection and prevention system (IDS/IPS).  
  - **tcpdump**: a packet analyzer for troubleshooting and monitoring network traffic.  
- This lab reinforced **Linux administration skills** directly applicable to system operations and cybersecurity tasks.  

---

## 📚 Key Skills Demonstrated
- **Git and UNIX commands** for .md file management and workflow  
- Linux package management with **APT**.  
- Installation, verification, and removal of software packages.  
- Use of network monitoring and intrusion detection tools.  
- Clear technical documentation for cybersecurity portfolios.  

---

*This activity demonstrates the ability to manage Linux software effectively while applying tools commonly used in cybersecurity operations.*

