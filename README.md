minesweeper-angular-rails
=========================
help from here: https://gorails.com/setup/ubuntu/13.04

setting up rails 4 on ubuntu 12.04
==================================
- install Ruby dependencies
```
sudo apt-get update
sudo apt-get install git-core curl zlib1g-dev build-essential libssl-dev libreadline-dev libyaml-dev libsqlite3-dev sqlite3 libxml2-dev libxslt1-dev libcurl4-openssl-dev python-software-properties
```

- install Ruby and RVM
```
sudo apt-get install libgdbm-dev libncurses5-dev automake libtool bison libffi-dev
curl -L https://get.rvm.io | bash -s stable
source ~/.rvm/scripts/rvm
echo "source ~/.rvm/scripts/rvm" >> ~/.bashrc
rvm install 2.1.3
rvm use 2.1.3 --default
ruby -v
```

- tell Rubygems not to install the documentation for each package locally
```
echo "gem: --no-ri --no-rdoc" > ~/.gemrc
```

- install NodeJS (necessary to enable Rails' Asset Pipeline)
```
sudo add-apt-repository ppa:chris-lea/node.js
sudo apt-get update
sudo apt-get install nodejs
```

- install Rails (and validate install)
```
gem install rails
rails -v
# Rails 4.1.6
```

