1) Connect to ssh
2) sudo apt update && sudo apt upgrade
3) reboot
4) sudo raspi-config
5) go to 7 Advanced Options
6) go to A3 Memory split 
7) set 512mb
8) Finish and reboot
9) sudo nano /boot/cmdline.txt
10) Add consoleblank=0 
11) sudo nano /etc/rc.local
12) Delete all and paste this code (enter your rstp stream before insertion)
13) reboot