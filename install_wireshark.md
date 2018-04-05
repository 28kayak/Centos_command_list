## Install the newest wireshark to Centos 7 
you can download the old version of wireshark by 
```sh
yum install wireshark 
```
In order to install the newer version, we will do the following:

1. Install required for compilers and so on.
```sh
sudo yum install gcc gcc-c++ bison flex libpcap-devel qt-devel gtk3-devel rpm-build libtool c-ares-devel qt5-qtbase-devel qt5-qtmultimedia-devel qt5-linguist desktop-file-utils
```
2. Download package of the wireshark from its official website   
[Wireshark](https://www.wireshark.org/#download )  
- select `source code` for Linux Opereting System 

3. Extract the package 

4. Execute configure file 
```sh
cd wireshark-2.4.6
./configure 
```
- if you get some warnings, like below, then you might get your hands dirty. 
```sh
lz4-devel is needed by wireshark-2.4.6-1.x86_64  
snappy-devel is needed by wireshark-2.4.6-1.x86_64  
libnghttp2-devel is needed by wireshark-2.4.6-1.x86_64  
```



- In my case, I need to install three libraries 
```sh
sudo yum install libgcrypt libgcrypt-devel gcc-c++
sudo yum install snappy-devel
sudo yum install libnghttp2-devel
```

5. Generate RPM package 
```sh
make rpm-package
```
-  in my case, some liberaries are not installed, so install them with the following command:
```sh
sudo yum install epel-release
sudo yum install lz4
sudo yum install lz4-devel
sudo yum install snappy-devel
```
- if you get the following message, then you can successfully generate RPM package. 
```sh
Package successfully built in /home/kaya/Applications/wireshark-2.4.6/packaging/rpm/RPMS.
```
6.  Check the package 
```sh
cd ./packaging/rpm/RPMS/x86_64
ls 
wireshark-2.2.11-1.x86_64.rpm      wireshark-qt-2.2.11-1.x86_64.rpm
```
7.  Install the two of rpm files with using yum 
```sh
yum install wireshark-2.2.11-1.x86_64.rpm

yum install wireshark-qt-2.2.11-1.x86_64.rpm
```

8.  Open wireshark 
```sh
wireshark 
```
![wireshark](https://github.com/28kayak/Centos_command_list/blob/master/img/screenshot_wireshark.png)


9.  Chnge permission 
![permission_denied](https://github.com/28kayak/Centos_command_list/blob/master/img/error.png)










## Reference 
-  [工作者（kousakusya）のブログ](https://ameblo.jp/kousakusya/entry-12341271788.html)
-  [libnghttp2-devel-1.21.1-1.el7.x86_64.rpm](https://centos.pkgs.org/7/epel-x86_64/libnghttp2-devel-1.21.1-1.el7.x86_64.rpm.html)  
-  [snappy-devel-1.1.0-3.el7.x86_64.rpm](https://centos.pkgs.org/7/centos-x86_64/snappy-devel-1.1.0-3.el7.x86_64.rpm.html)
