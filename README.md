blackjack-angular-rails
=======================
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
# ruby 2.1.3pxxx [...]
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

- install Rails
```
gem install rails
rails -v
# Rails 4.1.6
```

- install Postgres
```
sudo sh -c "echo 'deb http://apt.postgresql.org/pub/repos/apt/ precise-pgdg main' > /etc/apt/sources.list.d/pgdg.list"
wget --quiet -O - http://apt.postgresql.org/pub/repos/apt/ACCC4CF8.asc | sudo apt-key add -
sudo apt-get update
sudo apt-get install postgresql-common
sudo apt-get install postgresql-9.3 libpq-dev
psql --version
# psql (PostgreSQL) 9.3.5
```

- set up Rails user/pass for Postgres
```
sudo -u postgres createuser rails -s
sudo -u postgres psql
postgres=# \password rails
# enter new pass
```
