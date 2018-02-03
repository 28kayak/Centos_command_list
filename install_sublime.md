# Install sublime text from a terminal 

## Install the GPG key: 
```sh
sudo rpm -v --import https://download.sublimetext.com/sublimehq-rpm-pub.gpg
```
- GPG key (GNU Privacy Guard Key) is a hybrid-encryption software because it uses a combination of symmetric-key and public key cryptography. 
- In Linux, it checks if the packages, downlording via the internet by `apt-get` and `yum`, is coming from the correct distoributer.  
## select the channel to use 
`stable` 

```sh
sudo yum-config-manager --add-repo https://download.sublimetext.com/rpm/stable/x86_64/sublime-text.repo
```

`Dev` 
```sh
sudo yum-config-manager --add-repo https://download.sublimetext.com/rpm/dev/x86_64/sublime-text.repo
```
## Update yum and install sublime-text 
Run the following command:
```sh
sudo yum install subime-text
```

# Setup symbolic link (symlink) 
Run the following command:
```sh
sudo ln -s /opt/sublime_text/sublime_text /usr/local/bin/subl
```
## Launch Sublime from terminal 
```sh
subl test.txt 
```




# Reference
## for installation 
https://www.sublimetext.com/docs/3/linux_repositories.html
https://askubuntu.com/questions/273034/lauching-sublime-text-from-command-line

## About GPG key 
http://itpro.nikkeibp.co.jp/article/Keyword/20091204/341579/?rt=nocnt

https://en.wikipedia.org/wiki/GNU_Privacy_Guard


