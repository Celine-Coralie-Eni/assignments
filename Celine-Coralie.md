Section 1
1. B
2. The difference between the BIOS and the UEFI is that the BIOS uses the MBR(Master Boot Record) which supports atmost four partitions while the UEFI uses the GPT(GUID Partition Table) which supports 128 partitions on each device.
3. To determine which kernel modules ar loaded in the system use the command ```lsmod``` and to load a new module named dummy use the command ```sudo modprobe dummy```.
4. >The /proc directory contains information about running processes such as memory usage and it also provides information about system hardware like about device information and it also allows users to be able to view and modify kernel parameters and with this directory you can also view disk partitions and network interfaces too.
   >The /sys directory stores system files providing information about loaded kernel mmodules and system hardware iformation and also stores information about mounted systems and their properties.

Section 2
5. C
6. dpkg is a low-level package manager that installs, removes and manage debian packages and it also handles package dependencies and it only works with packages which have already been installed while apt is a highlevel package manager which manages packages and their dependencies and they also retreive packages from repositories and with apt, you can equally update and upgrade.
7. ```sudo apt autoremove```

Section 3
9. B
10. ```cat /var/log/syslog | grep "error" | wc -l```
11. >Hard links point directly to the data(inode) on the disk while soft links point to the path of a file.
    >With hard links, if the original file is deleted the data is not lost as far as there is still at least one hard link pointing to it while with soft links, if the original file id deleted the soft link becomes a broken link because it points to a path that no longer exists.
    >Hard links do not work across different filesystems while soft links can point to files or directories in another filesystem.
    >You cannot create a hard link to a directory but soft links can be created to both files and directories.
    To create a hard link you input the command ```ln file.txt hardlink.txt```
    To create a soft link you input the command ```ln -s file.txt softlink.txt
12. ```sudo find /etc -type f -name "*.conf" -mtime -7```
13. The cron daemon is a backgroung process that runs continuously for the purpose of repeating scheduled tasks and it allows you to schedule scripts or even commands to run at regular intervals. The purpose of it is to automate repetitive tasks ensuring efficient system maintenance.
    An example of a cron job that runs a script backup.sh every day at midnight is as follows:
    Open the crontab -e and add this job " 0 0 * * * /path/to/backup.sh "

Section 4
14. B
15. ```blkid -s UUID```
16. 
17. >Firstly, you have to idenrify the new disk using the command ```lsblk```. Then note the device name for example, /dev/sdb
    >Then create a new partition with the command ```sudo fdisk /dev/sdb``` and exit the fdisk with the w option and specify the partition number e.g, /dev/sdb1
    >Format the partition with the ext4 using the command ```sudo mkfs.ext4 /dev/sdb1```
    >Now mount the partition ```sudo mount /dev/sdb1 /data```
    >Then add an entry to the /etc/fstab for permanent mounting ```echo "/dev/sdb1 /data ext4 defaults 0 2" >> /etc/fstab"
    >Remount the partition ```sudo mount -a```
18. 
