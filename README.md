# Linux
---

### RESOURCES
---
Tech With Tim - https://www.youtube.com/playlist?list=PLzMcBGfZo4-nUIIMsz040W_X-03QH5c5h

### REMOTE TERMINAL
---
PUTTY  
SUPERPUTTY

### COMMAND
---
ls  
cd  
clear  
touch  
pwd  
cat  
mv  
cp  
rm
> rm *.txt (REMOVE ALL FILES WITH .txt EXTENTION) 

rmdir  
grep
> -n - DISPLAY LINE NUMBER  
> -C # - DISPLAY BEFORE & AFTER # LINES FROM THE MATCH  

rgrep
> find . | xargs grep "SEARCH" (IF RGREP DOESN'T EXIST)  

find
> find . -name "\*.txt$" (FIND FILES WITH .txt EXTENTION)  
> find . -type d -name something (FILE DIRECTORIES WITH something)  
> find . -type f -exec grep -l 'SEARCH STRING' {} \; | xargs grep -l 'ANOTHER TEXT' (DISPLAY FILES CONTAINING SEARCH STRINGS)  
> find . -maxdepth 1 -type f -name "\*.txt" -delete (DELETE FILES BASED ON SEARCH STRINGS)  
> find . -maxdepth 1 -type f -name "\*2020.txt" - exec mv '{}' ./DIRECTORY/ \; (MOVE FILES BASED ON SEARCH STRINGS)

head/tail  
scp
> scp -r {FILE} {ACCOUNT}@{DESTINATION SERVER}:{DESTINATION PATH}

ln (SYMBOLIC LINK)
> ln -s {PATH FROM} {PATH TO}

### COMMON ARGUMENTS
---
-r - RECURSIVE  
-f - FORCE  
-i - INTERACTIVE  

### APT COMMANDS
---
> sudo apt update  
> sudo apt upgrade  

### ROOT DIRECTORIES
---
bin - USER EXECUTABLE FILES  
boot - FILES REQUIRED TO BOOT OS  
dev - FILES RELATED TO HARDWARE DEVICES (HARDWARE INFORMATION)  
etc - LOCAL SYSTEM CONFIGURATION  
home - STORAGE FOR USER FILES (ROOT DIRECTORY IS AT root)  
lib - LIBRARY FILES TO BOOT OS  
media - MOUNT EXTERNAL/REMOVABLE MEDIA DEVICES (EX. USB)  
mnt - MOUNT TEMPORARY FILE SYSTEM  
opt - OPTIONAL FILES  
root - ROOT DIRECTORY  
sbin - SA EXCUTABLE FILES  
tmp - TEMPORARY FILES (FILES CAN BE DELETED AT ANY TIME)  
usr - SHARABLE READONLY FILES  
var - VARIABLE FILES  

### USERS & GROUPS
---
USER
- USER INFORMATION FILE (GROUP, SHELL, ETC.)
  > /etc/passwd
- ADD USER
  > adduser {USER}
- DELETE USER
  > deluser {USER}
- UPDATE PASSWORD
  > passwd {USER}
GROUP
- CREATE GROUP
  > addgroup {GROUP}
- DELETE GROUP
  > delgroup {GROUP}
- APPEND GROUP TO A USER
  > usermod -a -G {GROUP} {USER}
- DELETE GROUP FROM A USER
  > usermod -d {USER} {GROUP}
SUDO
- SUDOER FILE
  > visudo
- GRANT SUDO ACCCESS USERS
  > {USER} ALL=(ALL:ALL) ALL
  > {USER} ALL={PATH TO COMMAND EX. /user/bin/top}
- GRANT SUDO ACCESS TO GROUPS
  > %{GROUP} ALL=/usr/bin/ls, /usr/bin/apt
- LOG IN AS ANOTHER USER
  > sudo -u {USER}

### PERMISSION
---
FILE PERMISSION
> drwxrwxrwx OWNER GROUP
- DIRECTORY/OWNER/GROUP/ALL
- r - READ
- w - WRITE
- x - EXCUTE

CHANGE PERMISSION
> chmod 777 {FILE}

### PROCESSES
---
PROCESS MONITOR
> top

KILL A PROCESS
> kill -9 {PID}

PROCESS STATUS
> ps -ef

### NETWORK
---
IP ADDRESS
> ifconfig  
> ip -4 addr  
> ip -6 addr  
(INET = IPV4 & INET6 = IPV6)

NETWORK STAT (NETWORK STATUS, PORT, ETC.)
> netstat  

CURL (GET/POST REQUESTS)
> curl {ADDRESS}  

PING
> ping {ADDRESS  

RSA KEYS
===
SSH PATH
> .{HOME DIR}/.ssh/  

GENERATE (PUTTYGEN CAN BE USED TO CREATE KEYS ON WINDOWS)
> ssh-keygen -t rsa  

ALLOW PUBLIC KEYS
> cat id_rsa.pub >> .ssh/authorized_keys

OR COPY THE CONTENT OF THE PUBLIC KEY TO authorized_keys

### ENVRIONMENT
---
ENVRIONMENT VARIABLE
- $PATH - LIST OF DIRECTORIES YOUR SYSTEM LOOKS FOR EXECUTABLE FILES
- $USER - THE USER NAME
- $HOME - DEFAULT PATH TO THE USER'S HOME DIRECTORY
- $EDITOR - DEFAULT PATH TO EDITOR
- $UID - USER'S UNIQUE ID
- $TERM - DEFAULT TERMINAL EMULATOR
- $SHELL - DEFAULT SHELL

ENVIRONMENT FILE
> .profile (ENVIRONMENT VARIABLE)  
> .bashrc (BASH RELATED EX. EDITOR)  

TEMPORARY CHANGE
> export {VARIABLE NAME}={VALUE} (EX. export EDITOR=vi)  
> unset {VARIABLE NAME}  

TO UPDATE ENVIRONMENT VARIABLE TO THE ENVRIONMENT FILE
> source {ENVIRONMENT FILE}  

SYSTEM WIDE (ALL USER ENVIRONMENT FILE)
> /etc/environment

### CRONTAB
---
CRONTAB FILES
> /var/spool/cron/crontabs  

EDIT
> crontab -e  

\* \* \* \* \* COMMAND (EX /user/bin/python /home/you/script.py)
- MINUTE, HOUR, DAY OF MONTH, MONTH, DAY OF WEEK
- */15 \* \* \* \* (EVERY 15 MINUTES)
- 0 15 \* \* \* (ONCE A DAY AT 15:00)
- 0, 30 15 \* \* \* (ONCE A DAY AT 15:00 AND 15:30

### SYSTEMD
---
> /lib/systemd/system

### SENDMAIL
---
LOG FILE
> /var/log/mail.log

### OTHER COMMANDS
---
COMMAND DESCIPRTION
> man {COMMAND}  
> whatis {COMMAND}  

UPTIME OF THE SYSTEM
> uptime  

MESSAGE TO A USER (mesg y/n TO ENABLE/DISABLE)
> write {USER}  

MESSAGE TO ALL USERS
> well HELLO  

LOGGED IN USERS
> who  

SORT
> sort {FILE}  
- -r TO REVERSE THE ORDER

SHUTDOWN
> shutdown
- -h # (SHUT DOWN AFTER # MINUTES)
- -r (RESTART)
