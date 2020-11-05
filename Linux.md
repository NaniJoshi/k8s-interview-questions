---
id: Linux
title: Linux
---

# Linux History
## What is Linux?
* Linux is a Kernel which is an interface between OS and Hardware.
* Linux used in 
    * Android
    * TV
    * Microwave Owen
    * Wi-Fi Routers
* Both GNU and Linux is OS

## What is GNU?
* Called it as GNU no Unix and it is a opensource tool works on any OS.
* Discoverd by 

## Practice Linux
* Katakoda
* VM - Virtual Box
* Cloud (AWS,AZURE,GCP,DIGITAL OCEAN)

## SSH
* ssh - Secure Shell
    * bash - Bourne Again Shell
    * W will give list of connected users

## passwordless connection
* ssh-keygen
* ssh-copy-id -i pvtkey user@ip
* eval `ssh-agent`
* ssh-add pvtkey
* authorized_keys
* ssh joshi@hostname-ip
* ssh -i pvtkey joshi@hostname-ip

## Linux file system
* / -- root directory
* /home directory is Users home directory
* when we create a user it will go under this dir.
   * like /home/madhu -- madhu user.

* /root is a super user home directory
* /dev is to store divices
* /tmp temparory folder once reboot system all files in this folder will erased.
* /etc is to store configuration files (any configuration)  
     * /etc/ssh_config (client) effects all users
     * ~/.ssh/config only one user
     * /etc/sshd_config (server side)
* /bin is to store all executables like ls,cd,etc.. for normal users -- binary
* /sbin is to admin related files like adduser,addgrp etc... for super users -- system binary
* /lib is to store all library files
* /var is to variable files -- like logs,emails,docker containers, etc...
* in /var for authorization logs /var/log/auth.log

# User Management
## Super user root
* super user is root
* ID is 0
* home dir. /root
* prompt is #

## Normal user
* user is : madhu,joshi
* home dir. : /home/joshi, /home/madhu
* Id : 1000,1001, any specific
* Prompt is $
* to perform tasks as super user do sudo -s (user ubuntu only but perform task as root user)
* to switch to root user
     * sudo -s
     * sudo -i
     * sudo su -

## create user
* we can create user using following commands
    * adduser --> it will prompt for all the details of the user like password, name...etc...
    * useradd --> used for automation it will take care all the things
```
sudo useradd joshi -u 5000 -m -d /var/joshi -c "this is jenkins user"
     * -u is user id specific
     * -m for creating home dir.
     * -d path of the home dir.
     * -c to add comments like "this is jenkins user"
     * switch to created user "sudo su - joshi"    

sudo passwd jenkins --> for password      
```

## configuration files
* /etc/passwd --> password file
* /etc/shadow --> get the password
* /etc/group --> groups file

## making a normal user as super user
* sudo vi /etc/suoers 
* add jenkins user in that file as below
     * jenkins  all=(all:all)  all
* test sudo
     * su - jenkins
     * sudo ls

# File Management
## Create a Directory
``` 
mkdir class10 --> creates only class10
mkdir -p class10/maths --> creates parent dir class10 and under that maths
mkdir -p class10/{maths,sciense,telugu} --> creates parent dir and inside that creates multiple dir
```

## delete directory
```
rmdir class10 --> removes dir if only that dir is empty
rm -rf class10 --> remove forcefully
```

## copy files and directories
```
cp /home/madhu/a /home/joshi/b --> it will copies file a to file b in the from source path to destination path
```
* cp -r  --> is to copy directories
* cp -p --> it will preserve the permissions while copying i.e owner remains same.

   * src and destination are different
   * src is current and dest is different
   * src and dest are in the current dir.
   * dest is current dir and src is different

* absolute path --> from /root like /home/madhu/a
* relative path --> from current dir. like madhu/a
* . represents current directory 
* .. represents Parent directory

# Change Directory command cd
## used to change the directory
* cd (will move to home directory)
* cd ~ (same as above)
* cd - (previous directory)
* cd ..(parent directory)
* cd . (current directory no change)

# List command
## list command is used to list all the files in the directory
* ls 
     * ls -lrth
        * l --> long list
        * r --> reverse
        * t --> time
        * h --> human readable
     * d rwx rwx rwx
     * first charecter 
        * d is direcory
        * - is for mormal file
        * c is for cherecter files
        * l is for link files
        * s for socket files
     * Next 3 chars
        * rwx (owner/user permissions)
     * Next 3 chars
        * rwx (group permissions)
     * Next chars
        * rwx (others permissions)      
* ls -la
     * first column --> permissions
     * second cloumn --> user/owner
     * third --> group
     * fourth --> size
     * fifth --> date and time
* chmod --> permissions
* chown --> change ownership
* chgrp --> change group
* pwd --> show the current path
* touch --> to change the timestamp if the file already exists and to create the empty file     
* mv --> move file to destination and removes src one         
* ln --> like shortcut in windows
* tar
* zip
* rsync
* scp --> scp ip:src ip:dest

## redirections
* ">" override
* ">>" append content to last
* "<" input to the command
* "2>, 2>&1" --> redirects only errors and success to the file

# vi editor
## vi editor in linux
* insert mode : 
    * i --> insert
    * shift+i --> begining of the line
    * a --> append
    * shift+a --> append at the end of the line
    * o --> next line
    * shift+o --> above line 
    * cw --> change word
    * ~ --> to make letter into upper or lower case
    * r --> replaces one charecter
    * shift+r --> replace entire word
    * shift+c --> change word from cursor to end of the line
    * 3cw --> change 3 words

* Cursor modes : 
    * :10 --> take you to 10th line
    * gg --> beginig of the file
    * shift+g --> end of file
    * :set nu --> prints line numbers
    * j --> down
    * k --> up
    * l --> right
    * h --> left

* Copy and Paste :
    * yy --> single line copy
    * 10yy --> 10 lines copy
    * p paste
    * dd --> cut
    * 10dd --> cut 10 lines
    * 10p --> paste 10 times
    * yw --> copy word
    * dw --> delete word
    * x --> delete char
    * 5x --> delete 5 chars
    * d+shft+g --> delete from cursor to end of line
    * dgg --> delete from cursor to beging of line

* Undo :
    * esc u
* search :
    * /+word
    * /string\c ignore case
    * /\t search for tabs
    * /\s search for spaces            

# Process management
## To find running processes
* ps aux|grep apache2/httpd
* service apache2 status
* systemctl status apache2.service

## kill
* kill 15 is default kill
* kill 9 is immediate kill/abrupt kill
* sudo pkill apache2 --> using program name

## network processes :
* netstat
* top
* free -h --> ram details / human readable
     * buffer can be used for that perticular time
     * cache --> can be used many times
* uptime --> shows load and from when it is up

## How to clear buffer/cache memory in linux?
```
sync; echo 1 > /proc/sys/vm/drop_caches
sync; echo 2 > /proc/sys/vm/drop_caches
sync; echo 3 > /proc/sys/vm/drop_caches
```

## how to calculate load average
* (load/no. of cpu's)*100

## Disk management
* df -h --> disk memory df -s disk free
* du -sh --> disk usage
* iostat --> install systat
* lscpu --> list of cpu's
* /proc/cpuinfo --> cpu info
* vmstat --> gives total system info

## Grep : General Regular Expression and Pattern
* pa aux|grep ^ubuntu --> search for word from begining of the line
* ps aux|grep d$ --> shows process ending with d
* -v --> inverse
* ^$ --> empty lines
* ^string$ --> total line
* cat /etc/apache2/apcahe2.conf |grep -v "#"|grep -v "^$"
* -X exact line
* -w Word match

# search and replace commands
## sed --> stream editor (row wise editing)
* search --> /pattern

## regex
* [0-9] --> numbers, [] for or and - is for range
* [a-z][A-Z] --> 
     * [0-9]{2} --> {}for multiplication 
     * () --> for grouping
     * {n,m} multiplication and
     * /[0-9]\{2\} --> example for searching 2 digit numbers.
     * /[0-9]\{1,3\}\.[0-9]\{1,3\}\.[0-9]\{1,3\}\.[0-9]\{1,3\} --> to search ip addresses
     * /sudh?an --> ? is for preceeding character should be 0 or 1 time
           * "*" is for 0 or many --> /sudh*an
           * "+" is for 1 or many --> /sudh+an

## find
link : https://www.tecmint.com/35-practical-examples-of-linux-find-command/
```
find path -name "string"
```
