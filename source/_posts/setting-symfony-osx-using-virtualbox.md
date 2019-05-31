---
title: Setting up PHP and Symfony on OSX using VirtualBox Ubuntu 14.04
url: 708.html
id: 708
comments: false
categories:
  - Sketch
date: 2016-05-30 10:30:18
tags:
---

1.  Install Virtual Box with Ubuntu 14.04 LTE
2.  [Install Guest Additions ](http://en.ig.ma/notebook/2012/virtualbox-guest-additions-on-ubuntu-server)
3.  Optional: [install ssh so you can use your OSX terminal](https://www.quora.com/How-can-I-ssh-into-my-VM-from-the-Mac-OS-X-host) and remote in
4.  Install symfony - sudo curl -LsS https://symfony.com/installer -o /usr/local/bin/symfony
5.  sudo chmod a+x /usr/local/bin/symfony
6.  Set timezone, locale and hostname:
    
    `sudo` `dpkg-reconfigure tzdata`
    
    `sudo` `locale-gen en_NZ.UTF-8`
    
    `sudo` `vim` `/etc/hosts`
    
    `sudo` `echo` `"web.address"` `>` `/etc/hostname`
    
7.  Install your dev stack - sudo apt-get install <packages>. Mine is as follows:
    1.  PHP `sudo apt-get install mysql-client php5 php5-cli php5-mysql npm nodejs-legacy php5-gmp php5-curl php5-gd php5-mongo php5-fpm php5-dev mcrypt libpcre3-dev php5-mcrypt git openjdk-7-jre-headless curl acl wget ntp ntpdate -y`
    2.  MySQL server `sudo apt-get install mysql-server mysql-client mysql-utilities mysqltuner -y sudo npm -g install less bower`
    3.  Mongodb `sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 7F0CEB10 echo "deb http://repo.mongodb.org/apt/ubuntu "$(lsb_release -sc)"/mongodb-org/3.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-3.0.list sudo apt-get update sudo apt-get install -y mongodb-org`
8.  [Install Composer](https://getcomposer.org/download/)
9.  Clone your repo into /var/www/ then cd to dir
10.  Install symfony dependencies
    
    `# Set SYMFONY_ENV to dev, if not yet done`
    
    `export` `SYMFONY_ENV=dev`
    
    `SYMFONY_ENV=dev` `composer``.phar -o` `install`
    
11.  Setup your parameters.yml file with the correct settings
12.  npm install / bower install if necessary NB - dont forget to set your "path to node" in your parameters file. In my case they were: `path_to_node: /usr/bin/node path_to_node_modules: /usr/local/lib/node_modules`
13.  Install your symfony project assets. For me: `php app``/console` `assets:``` `install` ``
    
    `php app``/console` `assetic:dump`
    
    `php app``/console` `fos:elastica:populate`
    
14.  Run your web server. For me: `php app``/console server:start`