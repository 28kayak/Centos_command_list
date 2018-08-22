# Install Apache Solr 7.4.0 to Linux (Centos 7)
Date Installed:  08,21,2018 

# Pre-requirements 
 - A server running CentOS 7. 
 - A non-root user with sudo privilege setup on your server
 - Installed Java

# Updating yum and Installing Java 
Before installing Apache Solr, we need to update yum.
` sudo yum update `

Check your java version. 
` java -version `
output will be: 
```sh
openjdk version "1.8.0_181"  
OpenJDK Runtime Environment (build 1.8.0_181-b13)
OpenJDK 64-Bit Server VM (build 25.181-b13, mixed mode)
```
if you do not get the result above, then you will run 
```sh
sudo yum install java-1.8.0-openjdk.x86_64
```

# Download Apache Solr
download Apache Solr from the following URLs.
- `http://apache.org/dist/lucene/solr/7.4.0/solr-7.4.0.tgz` 
- `http://ftp.tsukuba.wide.ad.jp/software/apache/lucene/solr/7.4.0/`

check files are collectly downloaded (make sure you have )
```sh
 tar tzf solr-7.4.0.tgz 
```
It will show you as below:
```sh
solr-7.4.0/LUCENE_CHANGES.txt
solr-7.4.0/contrib/analysis-extras/lib/
solr-7.4.0/contrib/clustering/lib/
solr-7.4.0/contrib/dataimporthandler-extras/lib/
solr-7.4.0/contrib/extraction/lib/
solr-7.4.0/contrib/langid/lib/
solr-7.4.0/contrib/prometheus-exporter/conf/
solr-7.4.0/contrib/prometheus-exporter/lib/
solr-7.4.0/contrib/uima/lib/
....cont....
```
You can see that it will create directory named as `solr-7.4.0`.
So, you will extract the compressed file without creating another directory. 
```sh
tar xzf solr-7.4.0.tgz 
```
Then, move to the direcoty `bin`.
```sh
cd solr-7.4.0/
cd bin/
```
Now, install solr by running `install_solr_service.sh`, which is under bin directory.
```sh
sudo bash ./install_solr_service.sh ~/solr-7.4.0.tgz
```
After installing, it will run solr automatically. 
So, access to the following URL.
`http://localhost:8983/solr/#/`

![Solr Admin](https://github.com/28kayak/Centos_command_list/blob/master/img/Screenshot_Solr_Admin.png)  


# Reference 
- [Apache Solr Ref Guide](http://ftp.meisei-u.ac.jp/mirror/apache/dist/lucene/solr/ref-guide/apache-solr-ref-guide-7.4.pdf)
- [Install and Configure Apache Solr on Centos 7](https://devops.profitbricks.com/tutorials/install-and-configure-apache-solr-on-centos-7/)




**Free Software, Hell Yeah!**
