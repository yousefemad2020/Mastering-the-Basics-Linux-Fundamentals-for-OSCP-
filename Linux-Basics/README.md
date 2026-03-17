
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
<a name="advanced-bash"></a>
# 🚀 Part 2: Advanced Bash & Environment Mastery

In this section, I document my progress through lessons 1 to 9, focusing on how to control the Linux environment and customize my workflow for efficiency.

---

## 📄 Page 1: The Bash Environment 🌐
Understanding variables is essential for running scripts and tools in Kali Linux.

* **Environment Variables**: I learned to use the `env` command to list all active variables. 
* **The PATH Variable**: This is the most important variable. It tells Linux which folders to search for executable commands.
* **Local vs. Exported Variables**: 
    - A local variable: `name="yousef"` (Only stays in the current terminal).
    - An exported variable: `export name="yousef"` (Stays active even if you open a sub-shell like typing `bash`).

> 💡 **Tip:** Always use `echo $VARIABLE_NAME` to check the value.

---

## 📄 Page 2: Customizing the Environment 🛠️
To work faster, we can change how the terminal behaves.

* **Aliases (Shortcuts)**: I learned how to create "nicknames" for long commands.
    - Example: `alias ll='ls -lah'` allows me to see hidden files with just two letters.
* **The .bashrc File**: This is a hidden file in the home directory (`~/.bashrc`). 
* **Permanent Changes**: I added my custom exports and aliases to the end of this file so they load automatically every time I open the terminal.
* **Updating Changes**: Use `source ~/.bashrc` to apply changes immediately without restarting.

---

## 📄 Page 3: Command History Tricks 📜
Speed is key during the OSCP exam. These tricks save a lot of time:

* **Repeat Last Command**: Type `!!` to run the last command again (very useful with `sudo !!`).
* **Search History**: Use `history` to see a list of past commands.
* **Run by ID**: Use `!number` (e.g., `!42`) to run the command at that specific line in your history.
* **Reverse Search**: Press `Ctrl + R` to search for a command you typed previously.

---

## 📄 Page 4: Redirection & Pipes 🔗
This is how we "chain" commands together like a professional.

* **Piping (`|`)**: Sending the output of one command to be the input of another.
    - *Example*: `env | grep PATH` (Finds the PATH variable inside the environment list).
* **Redirection (`>`)**: Saving command output into a file instead of showing it on the screen.
    - `ls > files_list.txt` (Creates or overwrites a file).
    - `ls >> files_list.txt` (Appends/Adds to the end of an existing file).

---

## 📄 Page 5: Process & Package Management 📦
Keeping the system under control during a penetration test.

* **Monitoring Processes**: Using `top` or `ps aux` to see what programs are using memory and CPU.
* **Controlling Tasks**: 
    - `Ctrl + C`: Stops a running command.
    - `Ctrl + Z`: Pauses a command and puts it in the background.
* **Managing Tools**: I practiced using `apt` and `dpkg` to install new security tools and keep Kali updated. 

---

### 📸 Lab Evidence
*(Note: Upload your latest screenshots to the `Linux-Basics/images/` folder and link them here)*

![Bash Environment and Aliases](images/Screenshot%20from%202026-03-17%2023-31-14.png)
![Customizing .bashrc](images/Screenshot%20from%202026-03-17%2023-49-56.png)

---

## 🔄 Roadmap & Updates
This repo is **under active development**. Every time I complete a new lab in CCNP or a new module in OSCP+, I will update the sections here.

**Next Steps:**
- [ ] Network Discovery (Nmap & Netdiscover)
- [ ] Exploitation Basics
- [ ] Privilege Escalation (Linux/Windows)

---

*Created with ❤️ by [Your Name/Username]*
