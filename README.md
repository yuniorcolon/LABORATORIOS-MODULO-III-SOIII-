#!/bin/bash
sudo nano /etc/default/grub
sudo grub2-mkconfig -o /boot/grub2/grub.cfg
sudo grep "timeout" /boot/grub2/grub.cfg
sudo reboot
mount -o remount,rw /sysroot
chroot /sysroot
sudo nano backup_home.sh
chmod +x backup_home.sh
./backup_home.sh
sudo nano ifconfig.sh
chmod +x ifconfig.sh
./ifconfig.sh
ip a
sudo dnf install openssh-server 
sudo systemctl start sshd
sudo systemctl enbale sshd
sudo systemctl status sshd
ls -l
mkdir .ssh
chmod 700 /.ssh
cd .ssh/
touch authorized_keys
chmod 600 authorized_keys
ls
nano authorized_keys
