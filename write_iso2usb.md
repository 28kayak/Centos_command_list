#Find Disk to Write

```sh
$ sudo -i   
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

