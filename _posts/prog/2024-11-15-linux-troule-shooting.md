---
layout: page
title: Linux trouble shooting
---

This is a compilation of ways of fixing shit on linux. I made it because, since I don't use them on a daily basis, when I do need them I have usually forgotten and sometimes it is hard to find them again (because search engines keep sucking more and more).

# TCP Ports

If you need to use a port, but it is already in use, you can do the following.
```bash
sudo netstat -tunlp      # returns all the PID currently in use by the system
sudo lsof -i TCP:3306    # returns the PID of the program using port 3306
```
Now you can evaluate if the process occupying that port matters or not. If it doesn't you can kill it using the processing doing`sudo kill -9 $PID`.

# Instaling Packages

Example: mysql-server installation fails.

```bash
# Remove all packages related to mysql-server
sudo apt-get purge mysql*
sudo apt-get remove --purge mysql*
sudo apt-get purge msql*
sudo apt auto-remove mysql*
sudo apt-get autoclean
sudo apt-get remove dbconfig-mysql 

# Remove any left over from the installation (if there are)
sudo vim /etc/apt/apt.conf.d
sudo apt-get remove dbconfig-mysql

# Make sure we don't have any mysql installed
dpkg -l | grep mysql

# Update the system
sudo apt update
sudo apt upgrade
sudo apt-get dist-update

# Attempt to install it again
sudo apt install mysql-server
sudo apt install mysql_secure_installation
```

# I Botched My GRUB