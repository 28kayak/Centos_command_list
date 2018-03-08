# Setup Ruby on Rails Enviroment 

## Required Tech
* [SourceTree] - to control versions on the github
* [node.js] - version 8.9.1
* rbenv - version 1.1.1 
* Ruby - version 2.4.2
* rails - version 5.1.1
* [git-repo-url]
* [dill] - to write md file
* bundler 

## Installation for Mac User 
### Install node.js
```sh
$ git clone https://github.com/nodejs/node.git
$ cd node
$ git checkout v8.9.1
```
build node
```sh
$ ./configure
$ make
$ sudo make install
```
once the installation is done, check the node version and npm version
if you get the following numbers, then it succeeded! 
```sh
$ node --version
5.5.1
$ npm --version
v8.9.1
```
## install rbenv
Assume you have already installed homebrew.
```sh
$ brew update
$ brew install rbenv ruby-build
```
## upgrade ruby-build and rbenv 
*Ones who installed rbenv right now, skip to read this section.* 
If you have already installed rbenv before, but your rbenv does not support ruby-versioin you want to use, then you need to upgrade rbenv through brew.

```sh
$ brew upgrade ruby-build 
$ brew upgrade rbenv
#check if your desired ruby version is in the list 
$ rbenv install -list 
Available versions:
  1.8.5-p52
  1.8.5-p113
  1.8.5-p114
  1.8.5-p115
  1.8.5-p231
  1.8.6
  1.8.6-p36
  ...
  2.4.2
  ...
  ***abbreviate***
  ...
```
If you can find your desired version from the list then it succeeded.
> Chips  
> when you try `brew upgrade ruby-build` or `brew upgrade rbenv`, you might face to `permission denided`. In that case, you change owner by the following command
$ sudo chown -R $USER /usr/local
then try again to install or upgrade.

# set up your rbenv
After checking the list of versions, you will install the specific one. In this case, you will install 2.4.2
```sh
#This may take a while. 
$ rbenv install 2.4.2

ruby-build: use openssl from homebrew
Downloading ruby-2.4.2.tar.bz2...
-> https://cache.ruby-lang.org/pub/ruby/2.4/ruby-2.4.2.tar.bz2
Installing ruby-2.4.2...
Installed ruby-2.4.2 to /Users/kaya/.rbenv/versions/2.4.2

$ rbenv global 2.4.2
$ rbenv versions
  system
* 2.4.2 (set by **********)
```
add path to the .bash_profile 
By adding path to .bash_profile, 
your computer prioritizes ruby that you installed from rbenv. 
```sh
#ruby that Mac originally has
$ ruby -v
ruby 2.0.0p648 (2015-12-16 revision 53162) [universal.x86_64-darwin16]

$ echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bash_profile
$ echo 'if which rbenv > /dev/null; then eval "$(rbenv init -)"; fi' >> ~/.bash_profile
$ source ~/.bash_profile

$ ruby -v
ruby 2.4.2p198 (2017-09-14 revision 59899) [x86_64-darwin16]
```
# install rails
```sh
 $ gem install rails --version 5.1.1
Fetching: activesupport-5.1.1.gem (100%)
Successfully installed activesupport-5.1.1
Fetching: rack-2.0.4.gem (100%)
Successfully installed rack-2.0.4
Fetching: mini_portile2-2.3.0.gem (100%)
...
***abbreviate***
...
Done installing documentation for activesupport, ....
24 gems installed
```
If you get this result, then you can go on to the next step.
# install bundler 
```sh
$ gem install bundler
Successfully installed bundler-1.16.1
Parsing documentation for bundler-1.16.1
Done installing documentation for bundler after 5 seconds
1 gem installed
```
# clone the project from git hub 
Assume you already have a github account 
```sh
git clone url/to/the/project
Cloning into 'project_name'...
...
Resolving deltas: 100% (12063/12063), done.
cd project_name
bundle exec ruby -v 
ruby 2.4.2p198 (2017-09-14 revision 59899) [x86_64-darwin16]
```
> Chips 
if you run:
bundle exec ruby -v 
our side of your ruby project, it will return the following error messege. 
`Could not locate Gemfile or .bundle/ directory`
So, make sure your working directory 

# install gems of the project 
Before executing `bundle install`, you need to install pg-gem, which works with postgressDB 
For some reasons, pg-gem is not automatically installed by `bundle install`

```sh 
$ brew install postgresql
==> Installing dependencies for postgresql: readline
==> Installing postgresql dependency: readline
==> Downloading https://homebrew.bintray.com/bottles/readline-7.0.3_1.sierra.bottle.tar.gz
....
....
==> Summary
🍺  /usr/local/Cellar/postgresql/10.2: 3,377 files, 39MB
# Then install pg 
gem install pg -v '0.21.0'
Building native extensions.  This could take a while...
...
1 gem installed
```
Now, execute bundle install 
```sh
$ bundle install
Fetching gem metadata from http://rubygems.org/...........
Fetching https://github.com/maengkom/activerecord-userstamp.git
...
...
Bundle complete! 66 Gemfile dependencies, 284 gems now installed.
Use `bundle info [gemname]` to see where a bundled gem is installed.
```
# set up database 
locate `development.sqlite3` under `/db`
```sh
$ bundle exec rails db:migrate
== 20170725190000 CreateMngActivityExpenses: migrating ========================
-- create_table(:mng_activity_expenses)
   -> 0.0034s
== 20170725190000 CreateMngActivityExpenses: migrated (0.0036s) ===============
...
***abbreviate***
...
== 20180226010101 AddSabarmetricsColumnsToPlayerWarRecords: migrated (0.2077s) 
```

Now, run the server 
```sh
$ bundle exec rails s
```
access to 
```sh
http://localhost:3000/
```


# Reference 
* [update-rbenv] -- to update rbenv
* [install-ruby-on-rails-on-Mac] -- to install and add path to .bash_profile
* [stack-on-pg] -- when stacking on the bundle install 


[//]: # (These are reference links used in the body of this note and get stripped out when the markdown processor does its job. There is no need to format nicely because it shouldn't be seen. Thanks SO - http://stackoverflow.com/questions/4823468/store-comments-in-markdown-syntax)

[SourceTree]: <https://www.sourcetreeapp.com/>
[dill]: <https://github.com/joemccann/dillinger>
[git-repo-url]: <>
[node.js]: <http://nodejs.org>
[update-rbenv]: <http://morizyun.github.io/ruby/rbenv-update-mac-homebrew.html>
[install-ruby-on-rails-on-Mac]: <https://qiita.com/narikei/items/cd029911597cdc71c516>
[stack-on-pg]: <https://qiita.com/youcune/items/5b783f7fde45d0fd4b35>
>


  
   
