
# Uninstall Java
```sh
rpm -e jdk1.8
rm -f jdk-8u201-linux-x64.rpm
```
.bashrc, .bash_profileからパスを消しました。
```sh
#check 
java -version
->command not found 

rpm -qa | grep jdk　
-> nothing to return 
```
