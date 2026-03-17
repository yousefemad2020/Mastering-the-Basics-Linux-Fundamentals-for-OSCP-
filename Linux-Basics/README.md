
# 🛡️ Mastering Kali Linux: My Journey to OSCP+  🚀

Welcome to my personal documentation repository! In this repo, I document everything I learn during my preparation for the **OSCP+** and my studies in **CCNP SCOR**. 

> **Goal:** To bridge the gap between Network Security and Penetration Testing. 🌐🔐

---

## 📑 Table of Contents
- [1. Getting Started with Kali](#setup)
- [2. Linux File System Hierarchy](#filesystem)
- [3. Essential Commands Cheat Sheet](#commands)
- [4. Service Management](#services)
- [5. Package Management](#packages)

---

<a name="setup"></a>
## 1. Getting Started with Kali 📥
Before hacking, we must ensure our environment is safe and ready.

* **Download:** Always get Kali from the official [Kali.org](https://www.kali.org/).
* **Integrity Check:** 🛡️ Crucial step! I use `sha256sum` to verify the ISO file. 
    ```bash
    sha256sum kali-linux-2024.x-vmware-amd64.7z
    ```
* **Kali Undercover:** A great tool to make Kali look like Windows 10/11. Useful for physical pentesting in public places! 🥸

---

<a name="filesystem"></a>
## 2. Linux File System Hierarchy 📂
Understanding where things live is key for privilege escalation and enumeration.

| Directory | Description | Importance for OSCP |
| :--- | :--- | :--- |
| `/root` | Home of the root user | Accessing flags/sensitive data 🚩 |
| `/etc` | System configuration files | Finding password hashes (passwd/shadow) 🔑 |
| `/var/log` | System logs | Clearing tracks / Enumeration 🕵️ |
| `/tmp` | Temporary files | Good place to upload exploits 📁 |
| `/bin` | Executable binaries | Basic tools like `ls`, `cp`, `mv` |

---

<a name="commands"></a>
## 3. Essential Commands Cheat Sheet 🛠️
The tools I use every day in the terminal:

### ✨ Navigation & Info
- `pwd`: Print working directory.
- `whoami`: Who am I logged in as?
- `clear`: Clean the screen.
- `man <tool>`: Read the manual. 📖
- `whatis` / `apropos`: Search for command descriptions.

### 📂 File Management
- `ls -alh`: List all files (even hidden) with details.
- `mkdir` / `rmdir`: Create/Delete directories.
- `cp` / `mv` / `rm`: Copy, Move, or Remove files. **(Careful with rm!)** ⚠️
- `find`: Find files by name or type.
    ```bash
    find / -name "config.php" 2>/dev/null
    ```

### 🌐 Networking
- `ifconfig`: Check IP address and interfaces.
- `ip a`: The modern way to show interface addresses.

---

<a name="services"></a>
## 4. Service Management ⚙️
In CCNP SCOR, we learn about protocols. In Kali, we manage them.

- **HTTP Service:** Useful for hosting files.
    ```bash
    sudo systemctl start apache2
    ```
- **SSH Service:** For remote access.
    ```bash
    sudo service ssh status
    ```
- **Check all services:**
    ```bash
    sudo systemctl list-unit-files
    ```

![Linux File System](Screenshot%20from%202026-03-16%2022-09-24.png)
---

<a name="packages"></a>
## 5. Package Management 📦
Keeping the tools updated:

- **Update Repo:** `sudo apt update`
- **Install Tool:** `sudo apt install <tool_name>`
- **Install .deb file:** `sudo dpkg -i package.deb`

---

## 🔄 Roadmap & Updates
This repo is **under active development**. Every time I complete a new lab in CCNP or a new module in OSCP+, I will update the sections here.

**Next Steps:**
- [ ] Network Discovery (Nmap & Netdiscover)
- [ ] Exploitation Basics
- [ ] Privilege Escalation (Linux/Windows)

---
*Created with ❤️ by [Your Name/Username]*
