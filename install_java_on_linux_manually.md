# Install Java(OpenJDK) on Linux Manually 

1. Download JDK 
```sh
# this is OpenJDK 11 
wget https://download.java.net/openjdk/jdk11/ri/openjdk-11+28_linux-x64_bin.tar.gz
tar xfz openjdk-11+28_linux-x64_bin.tar.gz 
```

2. Set JAVA_HOME and PATH 
edit ~/.profile 
```sh
JAVA_HOME="/home/vagrant/java/jdk-11/"
PATH=${JAVA_HOME}/bin:${PATH}
```
3. check 
```sh
$ java -version 
openjdk version "11" 2018-09-25
OpenJDK Runtime Environment 18.9 (build 11+28)
OpenJDK 64-Bit Server VM 18.9 (build 11+28, mixed mode)

$ javac -version
javac 11
```


# Archived OpenJDK
# Java 7
* OpenJdk 7 (GNU LICENSE)
```sh 
https://download.java.net/openjdk/jdk7u75/ri/openjdk-7u75-b13-linux-x64-18_dec_2014.tar.gz
```

* OpenJdk 7 (Oracle Binary Code License)
```sh 
https://download.java.net/openjdk/jdk7u75/ri/jdk_ri-7u75-b13-linux-x64-18_dec_2014.tar.gz
```

# Java 8
