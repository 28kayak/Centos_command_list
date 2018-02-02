# Find Disk to Write

```sh
#become root and super user 
$ sudo -i  
#find disks 
$ fdisk -l
```

and its result witll be:

```sh
Disk /dev/sda: 256.1 GB, 256060514304 bytes, 500118192 sectors
Units = sectors of 1 * 512 = 512 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes
Disk label type: dos
Disk identifier: 0x000b941d

   Device Boot      Start         End      Blocks   Id  System
/dev/sda1   *        2048     2099199     1048576   83  Linux
/dev/sda2         2099200   270020607   133960704   8e  Linux LVM
```
# Unmount USB 
Before writting ISO to USB device, make sure USB device is unmounted. 
To unmount:
```sh 
$umount /dev/sdb1
$umount /dev/sdb2
```
if a particion is not mounted, the result will :
```sh
$umount /dev/sdb2
umount: /dev/sdb2: not mounted
```
# Now Write! 
```sh
$dd bs=4M if=/WHERE_ISO_LOCATED/NAME_OF_ISO.iso of=/dev/sdb
```
The result will be:
```sh
1121+1 records in
1121+1 records out
4704262144 bytes (4.7 GB) copied, 400.12 s, 11.8 MB/s
```

# Reference 
https://www.linux.com/blog/how-burn-iso-usb-drive
