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

## Basic Linux Command:

```
ls:              The most frequently used command in Linux to list directories
pwd:             Print working directory command in Linux
cd:              Linux command to navigate through directories
mkdir:           Used to create directories in Linux
mv :             Move or rename files in Linux
cp:              copying files in Linux
rm:              Delete files or directories
touch:           Create blank/empty files
clear:           Clear the terminal display
cat:             Display file contents on the terminal
echo:            Print any text that follows the command
less:            Linux command to display paged outputs in the terminal
man:             Access manual pages for all Linux commands
uname:           Linux command to get basic information about the OS
whoami:          Get the active username
tar:             Command to extract and compress files in linux
more:            Linux command to display paged outputs in the terminal
grep:            Search for a string within an output
head:            Return the specified number of lines from the top
tail:            Return the specified number of lines from the bottom
diff:            Find the difference between two files
cmp:             Allows you to check if two files are identical
sort:            Linux command to sort the content of a file while outputting
zip:             Zip files in Linux
unzip:           Unzip files in Linux
service:         Linux command to start and stop services
ps:              Display active processes
kill:            Kill active processes by process ID or name
df:              Display disk filesystem information
mount:           Mount file systems in Linux
chmod:           Command to change file permissions
chown:           Command for granting ownership of files or folders
ifconfig:        Display network interfaces and IP addresses
traceroute:      Trace all the network hops to reach the destination
wget:            Direct download files from the internet
sudo:            Command to escalate privileges in Linux
whereis:         Locate the binary, source, and manual pages for a command
whatis:          Find what a command is used for
top:             View active processes live with their system usage
passwd:          Create or update passwords for existing users


```

## Advance Linux Command:
```

lscpu:              display information about the CPU architecture
lspci:              display list of PCI devices.
lsusb:              display list of usb devices.
df -h:              report file system space usage [-h: is a flag]
free -h:            Display amount of free and used memory in the system
hostnamectl:        Control the system hostname
lsb_release -a:     print OS information [-a is a flag].  Alternate : cat /etc/os-release

```
---

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
