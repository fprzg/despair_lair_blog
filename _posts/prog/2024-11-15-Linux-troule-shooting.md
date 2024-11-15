---
layout: page
title: Linux trouble shooting
---

# TCP Ports

```bash
sudo netstat -tunlp      # returns all the PID currently in use by the system
sudo lsof -i TCP:3306    # returns the PID of the program using port 3306
```

# Package Installing

Example: mysql-server installation fails.

```bash
sudo apt-get purge mysql*           #
sudo apt-get remove --purge mysql*  # 
sudo apt-get purge msql*            #
sudo apt auto-remove mysql*         #
sudo apt-get autoclean              # clean apt's cache
sudo apt-get remove dbconfig-mysql  #
sudo apt-get dist-update            #
sudo apt-get dist-upgrade           #

#sudo apt list --upgradable
#sudo apt upgrade
#sudo apt update
#apt list --upgradable
#sudo apt upgrade
#sudo vim /etc/apt/apt.conf.d
#sudo apt-get remove dbconfig-mysql
#dpkg -l | grep mysql
#sudo apt install mysql-server
#sudo apt install mysql_secure_installation
```
