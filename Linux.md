## Account:

**Three type of account on linux** 

1. Root account: Main Account with full power.
2. Service account: Installed with package
3. User account: Accounts with some power if it is given 

**Four type of administration file:**
```
/etc/passwd ⇒ User account full information
/etc/shadow ⇒ User encrypted password
/etc/group ⇒ hold group information
/etc/gshadow ⇒ hold group’s encrypted password
```

**To find which algorithm is used to encrypt the password in linux:**

if they start with (prefix) 
```
- $6$ ⇒ , means used SHA512
- $1$ ⇒ MD5
- $2a ⇒ Bluefish
- $5$ ⇒ SHA256
```
## Managing users & groups commands

- useradd → add account
- usermod → modify account attribute
- userdel → delete accounts
- groupadd → add groups
- groupmod → modifies groups
- groupdel → remove groups

---

## Permissions
**grants access to system resources, files, and folders and tell what you can do on the system.**

- **r → read [4]** 
- **w → write [2]**
- **x → executable [1]**
- **_ → no permission. [0]**

```

_ r w x r _ _ _ w _ 
0 1 2 3 4 5 6 7 8 9 ] ⇒ Total 10 character

```

0 → type ( whether file or directory (In linux folder is called directory) )

- **`_`** : Regular file
- **`d`**: Directory
- **`l`**: Symbolic link
- **`c`**: Character device
- **`b`**: Block device
- **`p`**: Named pipe (FIFO)
- **`s`**: Socket
- **`D`**: Door (used in some systems like Solaris)
- **`L`**: Link file (hard link)

**{1 2 3} → permission for user, In this case a user has rwx permission (read, write, execute)**

**{4 5 6} → permission for groups, In this case a groups has only r read permission.**

**{7 8 9} → permission for other users ( neither user nor group member ). In this case they have only write permission .**

**How to assign permissions? Using chmod command. Example → chmod +x filename (replace filename with your files and with + assign permission)**

~ **Note** Ensure you have proper power or privilege for assigning permissions to the files.

---
Nice cmd is used to set priority of the process . for non -root user the range belongs to +0 — +19 least priority 

Type: nice -n+15 find / -name “file-name”

for security reasons user limitation can be set by configuring limit.conf file 

`/etc/security/limits.conf`

renice - cmd is used to change the priority of running process .

— renice +15 -p 1163 [ -p is for process id flag 1163 is pid for GID -g and for UID -u ]

---

## Linux Commands
---
## 📁 File & Directory Management
```
ls               List files and directories
pwd              Show current working directory
cd               Navigate between directories
mkdir            Create a directory
rmdir            Remove empty directory
touch            Create an empty file / update timestamp
cp               Copy files or directories
mv               Move or rename files
rm               Remove files or directories
ln               Create hard or symbolic links
cat              Show file contents
less             View file contents page-by-page
more             View file contents (older)
head             Show first lines of a file
tail             Show last lines of a file
sort             Sort lines in a file
diff             Compare two files line by line
cmp              Compare files byte by byte
find             Search for files/directories
shred            Make content of file unreadable
mount            Mount file systems
tar              Create or extract tar archives
zip              Create zip archives
unzip            Extract zip archives
```

## 📝 Text Editing & Viewing
```
nano             Simple terminal editor
vim              Advanced terminal editor
echo             Print text
```

## 👤 User & Permission Management
```
whoami           Show current user
useradd          Add a new user
adduser          Friendlier user creation tool
su               Switch user
exit             Exit current user/shell
passwd           Change user password
chmod            Change permissions
chown            Change file ownership
sudo             Run command as superuser
```

## 🌐 Networking & Internet
```
ssh              Connect to remote machines
ifconfig         Show/assign IP (older)
ip address       Show detailed network info
ping             Test network connectivity
traceroute       Show path packets travel
curl             Transfer data to/from a server
wget             Download files from internet
netstat          Show network connections (older)
ss               Show socket statistics (modern)
iptables         Manage firewall rules
ufw              Simple firewall manager
resolvectl status Show DNS configuration
```

## 📦 Package & System Management
```
apt              Install/remove software packages
systemctl        Control services & system state
service          Manage services (older)
reboot           Restart system
shutdown         Shut down system
history          View command history
```

## 📊 Process & System Monitoring
```
ps               Snapshot of running processes
top              Real-time process viewer
htop             Enhanced interactive process viewer
kill             Kill a process by PID
pkill            Kill processes by name
free             Show RAM usage
df               Show disk usage
uname            Show system/kernel info
neofetch         Display system info visually
cal              Show calendar
clear            Clear screen
```

## 🔍 Searching & Information
```
grep             Search text using patterns
awk              Process/format text
man              Manual pages for commands
whatis           One-line command description
whereis          Locate command binary/source/manual
finger           Show info about system users
```

## Advance
```
lscpu:              display information about the CPU architecture
lspci:              display list of PCI devices.
lsusb:              display list of usb devices.
free -h:            Display amount of free and used memory in the system
hostnamectl:        Control the system hostname
lsb_release -a:     print OS information [-a is a flag].  Alternate : cat /etc/os-release
jobs:               to  displays the list of processes running in the background and specify job number. 
kill:               cmd used to kill jobs/processes by giving them signal code (

which is :

2  - SIGINT Immediate termination of the process
9  - SIGKILL Interrupt the process (ctrl + d)
15 - SIGTERM Clean termination of the process
18 - SIGCONT resume the processes
19 - SIGSTOP suspend the process

for example :-  kill -9 1664 
)

```

## Linux File System Hierarchy

**In Linux, everything is organized in a hierarchical directory structure. The root directory (`/`) is the top-most directory, and everything else is stored under it.**

## Common Directories in Linux
| **Directory** | **Description** | **Example Usage** |
| --- | --- | --- |
| `/` | **Root Directory** | The top-level directory where everything begins. All files and directories are under `/`. |
| `/bin` | **Binary Executable** | Contains essential system commands and binaries (like `ls`, `cp`, `cat`). |
| `/boot` | **Boot Files** | Contains files needed to boot the system (e.g., kernel files). |
| `/dev` | **Device Files** | Contains device files for hardware (e.g., `/dev/sda` for a hard drive). |
| `/etc` | **Configuration Files** | Contains system-wide configuration files (e.g., `/etc/passwd` for user information). |
| `/home` | **User Home Directories** | Each user has a personal directory here (e.g., `/home/john` for user "john"). |
| `/lib` | **Shared Libraries** | Contains system libraries needed by binaries (like `libc` for system calls). |
| `/media` | **Removable Media** | Mounted external devices (USB, CD/DVD drives, etc.) are found here. |
| `/mnt` | **Temporary Mount Points** | Used for temporarily mounting storage devices. |
| `/opt` | **Optional Software** | Contains optional software and third-party applications. |
| `/proc` | **Virtual File System** | Contains system and process information (e.g., `/proc/cpuinfo` for CPU details). |
| `/root` | **Root User’s Home Directory** | Home directory for the root user (the superuser). |
| `/run` | **Runtime Data** | Contains system information about the current boot session (e.g., running processes). |
| `/sbin` | **System Binaries** | Contains essential system binaries used by the superuser for system management. |
| `/srv` | **Service Data** | Contains data for services provided by the system (e.g., web server data). |
| `/sys` | **System Information** | Contains information about system devices and kernel. |
| `/tmp` | **Temporary Files** | Used for storing temporary files created by applications. |
| `/usr` | **User Programs and Data** | Contains non-essential user applications and files (e.g., `/usr/bin` for user binaries, `/usr/lib` for libraries). |
| `/var` | **Variable Files** | Contains files that vary in size, such as logs (`/var/log`), mail (`/var/mail`), and databases. |


---

## Graphical version of Directories in Linux. 
### [Source of image](https://www.linuxfoundation.org/blog/blog/classic-sysadmin-the-linux-filesystem-explained )
![standard-unix-filesystem-hierarchy-1](https://github.com/user-attachments/assets/ce8b32ac-e91b-4299-a19f-c5596f0a4af4)


