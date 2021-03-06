# Vagrant Ansible for CakePHP

Vagrant Ansible creates a Vagrant installation for CakePHP using Ansible with the following features:

- Ubuntu 12.04 Precise Pangolin
- Ningx 1.1
- PHP 5.5
- Percona 5.5 (MySQL Drop-in Replacement)
- Postgres 9.1
- Redis 2.8
- Memcached 1.4
- Git 1.7
- Composer


## Requirements

- [VirtualBox](https://www.virtualbox.org/wiki/Downloads). Tested on 4.3.x, but 4.2.x should also work.
- [Vagrant](http://www.vagrantup.com/downloads.html). Tested on 1.4.3
- [Ansible](http://docs.ansible.com/intro_installation.html). Tested on 1.4.4


## Installation

```
git clone git@github.com:FriendsOfCake/vagrant-ansible.git
cd vagrant-ansible
vagrant up
```

Note that this Vagrant machine uses NFS mounts as it significantly improves the speed of the application. You may be asked for the root password while trying to setup shared mounts.

The setup is take some time to finish. Sit back and enjoy!

When the setup is done browse to `http://192.168.13.37/` in your browser, and you should have some sort of `It works!` page!


### Custom Domain Name

Edit your /etc/hosts file to have the following line:

```
192.168.13.37 www.app.dev app.dev
```

Note that www.app.dev will actually redirect to app.dev


### Setup the Application

Anything in `app/webroot/index.php` will be served up, and all other `index.php` files ignored.

Below you can choose between two methods to create a new application.


#### Create new application with [cakephp/app](https://github.com/cakephp/app) for CakePHP 3.0.x:

```
composer -sdev create-project cakephp/app app
```

Browse to `http://app.dev`, an CakePHP application should be running now!

Follow more instructions on how to configure the application at [cakephp/app](https://github.com/cakephp/app).


#### Create new application with [FriendsOfCake/app-template](https://github.com/FriendsOfCake/app-template):

```
composer -sdev create-project friendsofcake/app-template .
```

Browse to `http://app.dev`, an CakePHP application should be running now!

Follow more instructions on how to configure the application at [FriendsOfCake/app-template](https://github.com/FriendsOfCake/app-template).


## Credits

This project was totally inspired from [FriendsOfCake/vagrant-chef](https://github.com/FriendsOfCake/vagrant-chef).

Many thanks to [josegonzalez](https://github.com/josegonzalez)!


## MIT

Copyright (c) 2014 Renan Gonçalves

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE
