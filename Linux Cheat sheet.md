## Linux Cheat Sheet

### File Commands:


directory listing:
```bash
ls
```  
![image](https://user-images.githubusercontent.com/3309836/208737625-5b412b93-aa98-43d4-9c9a-cc60fccb32e8.png)

formatted listing with hidden files and permissions:
```bash
ls -la
```    
change directory to dir:
```bash
 cd dir
```  
cd – change to home:
```sh
 cd -
``` 
show current directory:
```bash
pwd
``` 
dir – create a directory dir:
```bash
mkdir
``` 
delete file:
```bash
rm file
``` 
 delete directory dir
```bash
rm -r dir
```
force remove file:
```sh
rm -f file
```
```sh
force remove directory dir:
 rm -rf dir 
```
copy file1 to file2:
```bash
cp file1 file2
```
copy dir1 to dir2; create dir2 if it doesn't exist:
```bash
cp -r dir1 dir2
```
rename or move file1 to file2 if file2 is an existing directory, moves file1 into directory file2:
```bash
mv file1 file2
```
create symbolic link link to file:
```bash
ln -s file link
```
create or update file:
```bach
touch file
```
places standard input into file:
```bash
cat > file
```
output the contents of file:
```bash
more file
```
output the first 10 lines of file:
```bash
head file
```
```bash
output the last 10 lines of file:
tail file
```
output the contents of file as it grows, starting with the last 10 lines:
```bash
tail -f file
```

### Find files:
```bash
* find "$(pwd)" -name "<filename>" - find file and show full directory name
* find . -name "<filename>" -type f | xargs du -sh - 
* find . -type f ! -name "*.*"
* find . -name "*.<file-type>" -type f -delete
* find . -name "*.<file-type>" -exec rm {} \;
* find . -name "<directory-name>" -type d -exec rm -rv {} +
```

### LINUX User Profile Configuration
```bash
*     /bin/bash
*           The bash executable
*    /etc/profile
*           The systemwide initialization file, executed for login shells
*    /etc/bash.bashrc
*           The systemwide per-interactive-shell startup file
*    /etc/bash.bash.logout
*           The systemwide login shell cleanup file, executed when a login shell exits
*    ~/.bash_profile
*           The personal initialization file, executed for login shells
*    ~/.bashrc
*           The individual per-interactive-shell startup file
*    ~/.bash_logout
*           The individual login shell cleanup file, executed when a login shell exits
*    ~/.inputrc
*           Individual readline initialization file
* 
```
### Process Management:
```bash
* ps – display your currently active processes
* top – display all running processes
* kill pid – kill process id pid
* killall proc – kill all processes named proc *
* bg – lists stopped or background jobs; resume a stopped job in the background
* fg – brings the most recent job to foreground
* fg n – brings job n to the foreground
```


### Shutdown/Restart check:
``bash
* last reboot      # check boot log
* last -x shutdown # check shutdown log
```

### List all users:
```bash
less /etc/passwd
```

### Logical Processors counter:
```bash
echo $(nproc) # 4
```

### Copy file from remote host:
```bash
scp <username>@<ip-address>:/some/remote/directory/<original-name>.zip <new-name>.zip 
```

### Check status of the file:
```bash
stat <filename>
```
### Backup Linux system:
```bash
cd /
tar -cvpzf backup.tar.gz \
--exclude=/backup.tar.gz \
--exclude=/proc \
--exclude=/tmp \
--exclude=/mnt \
--exclude=/dev \
--exclude=/sys \
--exclude=/run \
--exclude=/media \
--exclude=/var/log \
--exclude=/var/cache/apt/archives \
--exclude=/usr/src/linux-headers* \
--exclude=/home/*/.gvfs \
--exclude=/home/*/.cache \
--exclude=/home/*/.local/share/Trash /
```

### File Permissions:
```bash
chmod octal file – change the permissions of file to octal, which can be found separately for user, group, and world by adding:
4 – read (r)
2 – write (w)
1 – execute (x)
```

### Examples:
```bash
chmod 777 – read, write, execute for all
chmod 755 – rwx for owner, rx for group and world
```

### SSH:
```bash
ssh user@host – connect to host as user
ssh -p port user@host – connect to host on port port as user
ssh-copy-id user@host – add your key to host for user to enable a keyed or passwordless login
```

### Searching:
```bash
grep pattern files – search for pattern in files
grep -r pattern dir – search recursively for pattern in dir
command | grep pattern – search for pattern in the output of command
locate file – find all instances of file
```

### System Info:
```bash
date – show the current date and time
cal – show this month's calendar
uptime – show current uptime
w – display who is online
whoami – who you are logged in as
finger user – display information about user
uname -a – show kernel information
cat /proc/cpuinfo – cpu information
cat /proc/meminfo – memory information
man command – show the manual for command
df – show disk usage
du – show directory space usage
free – show memory and swap usage
whereis app – show possible locations of app
which app – show which app will be run by default
```

### Compression:
```bash
tar cf file.tar files – create a tar named file.tar containing files
tar xf file.tar – extract the files from file.tar
tar czf file.tar.gz files – create a tar with Gzip compression
tar xzf file.tar.gz – extract a tar using Gzip
tar cjf file.tar.bz2 – create a tar with Bzip2 compression
tar xjf file.tar.bz2 – extract a tar using Bzip2
gzip file – compresses file and renames it to file.gz
gzip -d file.gz – decompresses file.gz back to file
```

### Network:
```bash
ping host – ping host and output results
whois domain – get whois information for domain
dig domain – get DNS information for domain
dig -x host – reverse lookup host
wget file – download file
wget -c file – continue a stopped download
```

### Installation:
```bash
dpkg -i pkg.deb – install a package (Debian)
rpm -Uvh pkg.rpm – install a package (RPM)
```

### Install from source:
```bash
./configure
make
make install
```
### Shortcuts:
```bash
Ctrl+C – halts the current command
Ctrl+Z – stops the current command, resume with
fg in the foreground or bg in the background
Ctrl+D – log out of current session, similar to exit
Ctrl+W – erases one word in the current line
Ctrl+U – erases the whole line
Ctrl+R – type to bring up a recent command
!! - repeats the last command
exit – log out of current session
```
