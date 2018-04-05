## Install the newest wireshark to Centos 7 
you can download the old version of wireshark by 
```sh
yum install wireshark 
```
In order to install the newer version, we will do the following:

1. install required for compilers and so on.
```sh
sudo yum install gcc gcc-c++ bison flex libpcap-devel qt-devel gtk3-devel rpm-build libtool c-ares-devel qt5-qtbase-devel qt5-qtmultimedia-devel qt5-linguist desktop-file-utils
```
2. Download package of the wireshark 
```sh
wget http://www.wireshark.org/download/src/wireshark-2.2.11.tar.bz2
```




lz4-devel is needed by wireshark-2.4.6-1.x86_64  


sudo yum install snappy-devel
snappy-devel is needed by wireshark-2.4.6-1.x86_64  
libnghttp2-devel is needed by wireshark-2.4.6-1.x86_64  



Package successfully built in /home/kaya/Applications/wireshark-2.4.6/packaging/rpm/RPMS.


## Reference 
-  [工作者（kousakusya）のブログ](https://ameblo.jp/kousakusya/entry-12341271788.html)
