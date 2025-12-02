#  Linux Interview Cheat Sheet 

---

## **1. What is Linux?**
Linux is a Unix-like, open-source operating system kernel created by Linus Torvalds. It powers servers, embedded systems, mobile devices, and desktops, and supports architectures like x86, ARM, and SPARC.

---

## **2. Basic Features of Linux**
- Free & open-source  
- Highly secure (password auth, auditing)  
- Own software repositories  
- Supports multiple languages  
- Offers CLI + GUI  
- Stable and efficient for server environments  

---

## **3. Common Linux Distros**
- Ubuntu  
- Debian  
- RedHat  
- Fedora  
- CentOS  

---

## **4. Linux vs Windows**

| Factor | Linux | Windows |
|-------|--------|----------|
| Free/Paid | Free & open-source | Paid, closed-source |
| Security | Highly secure | Less secure |
| Path Separator | `/` | `\` |
| Efficiency | More efficient | Less efficient |
| Kernel Type | Monolithic | Hybrid |
| Case Sensitivity | Case-sensitive | Case-insensitive |

---

## **5. Components of Linux**
- **Kernel** – Core program managing hardware  
- **Shell** – Interface between user & kernel  
- **GUI** – Graphical interface  
- **System Utilities** – OS management tools  
- **Applications** – Programs performing tasks  

---

## **6. File Permissions**
- **r** → Read  
- **w** → Write  
- **x** → Execute  

---

## **7. Linux Kernel**
A low-level program managing system resources.  
Released under **GPL**, so editing/modifying is legal.

---

## **8. LILO**
Linux Loader – a bootloader used to load Linux into memory.

---

## **9. Shell in Linux**
- **csh** – C Shell  
- **ksh** – Korn Shell  
- **zsh** – Z Shell  
- **bash** – Bourne Again Shell (default)  
- **fish** – Friendly Interactive Shell  

---

## **10. Root Account**
Superuser with full administrative access.

---

## **11. CLI vs GUI**
- **CLI:** Command-line interface for commands  
- **GUI:** Graphical interface using icons/windows  

---

## **12. Swap Space**
Used as virtual memory to extend RAM.

---

## **13. Hard vs Soft Links**

| Hard Link | Soft Link (Symlink) |
|-----------|----------------------|
| Contains actual data | Points to file path |
| Same inode | Different inode |
| Faster | Slower |
| No relative paths | Supports relative paths |
| Cannot link dirs | Can link dirs |
| Uses less memory | Uses more memory |

---

## **14. Create Symbolic Link**
```bash
ln -s <source> <link_name>
```
## **15. Standard Streams**
stdin – Input

stdout – Output

stderr – Error messages

# 🟦 Intermediate Linux
## **16. Mount/Unmount Filesystems
```bash
fdisk -l         # list disks
mkdir /mnt/p1    # create mount point
mount <partition> /mnt/p1
umount /mnt/p1
```
## **17. Troubleshoot Network Issues

*Check cables, connectivity*

Check IP: ip addr

Routes: ip route

DNS: /etc/resolv.conf

Firewall: ufw, iptables

Restart interface: ifup/ifdown

## **18. List Processes
```bash
ps -ef
ps auxf
top
htop
```
## **19. chmod Command
```bash
chmod u+wx file.sh
```
## **20. Check Disk Usage
```bash
df -h       # disk space
du -sh DIR  # directory size
ncdu DIR    # interactive disk usage
```
## **21. Find PID of Process
```bash
pgrep <name>
ps -e | grep <name>
```
## **22. rsync for File Sync
```bash
rsync -av source destination
rsync -avz --delete src dst
```
## **23. Create User
```bash
useradd username
passwd username
adduser username
```
## **24. Format Disk
```bash
lsblk
umount <partition>
mkfs.ext4 <partition>
mount <partition> /mnt/p1
```
## **25. Change User Password
```bash
passwd username
```
## **26. Process vs Thread
**Process**	
-Independent	Dependent
-More resource	
-Slower start	
-Separate memory

**Thread**
-shared memory
-Less resource
-Faster
-Shared memory
## **27. ulimit Command
```
ulimit -u 50    # set max processes
```
## **28. find Command
```
find ~/Downloads -name file.txt
```
## **29. RAID Levels
```
RAID 0: Striping

RAID 1: Mirroring

RAID 5: Striping + parity

RAID 6: Dual parity

RAID 10: RAID 0 + RAID 1
```
## **30. Challenges of Linux
```
Hardware compatibility

Gaming limitations

Steeper learning curve

Driver issues
```
# 🟥 Advanced Linux
## **31. /proc File System

Virtual filesystem showing kernel & process info.

## **32. Securing a Linux Server

Strong passwords

Firewall rules

SSH key auth

IDS tools

Regular updates

Log monitoring

## **33. strace

Trace system calls:
```
strace ls
```
## **34. Optimize Performance
```
Update system

Tune kernel parameters

Disable unused services

Monitor with PCP

Disk I/O optimization
```
## **35. Linux Server Administration
```
User management

Permission control

Backup strategy

Monitoring tools

Security configuration

Documentation & recovery planning
```
## **36. Virtual Memory

Uses disk space to extend RAM when needed.

## **37. Process Scheduling
Priority-based, preemptive algorithm used by Linux.

## **38. Important Commands
ls, mkdir, pwd

top, free, df

grep, cat, tar

wget, man

## **39. iptables
```
iptables -L
iptables -A <chain> <options> -j <target>
iptables-save > /etc/iptables/rules.v4
```
## **40. Troubleshoot Boot Issues
```
Check GRUB

Check logs

Boot using older kernel

Check hardware

Undo recent changes
```
## **41. init Process
First process on boot (PID 1).
Now replaced by systemd in many distros.

## **42. SMTP
SMTP → Simple Mail Transfer Protocol for sending emails.

## 2. What are the main components of a Linux system?
- **Kernel** – Core of the OS, manages hardware and system resources  
- **Shell** – Command-line interpreter  
- **File System** – Organizes files and directories

---

## 3. What is the role of the Linux kernel?
The Linux kernel **manages system resources**, such as CPU, memory, devices, processes, and provides essential services to applications.

---

## 4. What is a shell in Linux?
A shell is a **command-line interpreter** that accepts user commands and executes them.  
Examples: **Bash**, **Zsh**, **Fish**.

---

## 5. What are some popular Linux distributions?
- Ubuntu  
- Debian  
- Fedora  
- CentOS  
- Red Hat Enterprise Linux (RHEL)

---

## 6. How do you change file permissions in Linux?
Use the `chmod` command.

Example:
```bash
chmod 755 filename
This sets:

Owner → Read, write, execute

Group & Others → Read, execute
```
## 7. What is the purpose of the grep command?
grep is used to search for patterns in files and filter output.

Example:
```
grep "error" logfile.txt
```
## 8. How do you find files in Linux?
Use the find command.

Example:
```
find /path -name "file.txt"
```
## 9. What is the purpose of the top command?
top displays real-time system monitoring, including:

Running processes

CPU usage

Memory usage

##  10. How do you check disk usage in Linux?
Use the df command.

Example:

```bash
df -h
-h shows output in human-readable format.
```
## 11. What is a symbolic link in Linux?
A symbolic link (soft link) is a special file that points to another file or directory.

Create one with:
```bash
ln -s target_file link_name
```
## 12. What is the purpose of the tar command?
tar is used to create, extract, and manage archive files.

Example:
```bash
tar -cvf archive.tar folder/
```
## 13. How do you start and stop services in Linux?
On systemd-based systems, use:

Start service:
```bash
systemctl start service_name
```
Stop service:
```bash
systemctl stop service_name
```
Check status:
```bash
systemctl status service_name
```
## 14. What is the purpose of the ping command?

ping is used to test network connectivity by sending ICMP echo requests.

Example:
```bash
ping google.com
```
## 15. How do you check the network configuration in Linux?
Legacy command:

```bash
ifconfig
```
Modern command:
```bash
ip addr
```
or
```bash
ip a
```
---
