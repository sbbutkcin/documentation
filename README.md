[![Circle CI](https://circleci.com/gh/pantheon-systems/documentation.svg?style=svg)](https://circleci.com/gh/pantheon-systems/documentation)
[![Stories in Ready](https://badge.waffle.io/pantheon-systems/documentation.png?label=ready&title=Ready for Work)](https://waffle.io/pantheon-systems/documentation)
Pantheon Documentation
======================

Documentation Site
------------------

Visit https://pantheon.io/docs/ for the latest release of Pantheon documentation, which is:

-   Version-controlled
-   Forkable
-   Continuously updated
-   Written in markdown
-   Generated by [Sculpin](https://sculpin.io/)

### Contributing

Read [CONTRIBUTING.md](<CONTRIBUTING.md>) for more details on contributing
documentation improvements.

### Style Guide

Read [style-guide.md](<style-guide.md>) for our guidelines on how to write
documentation.

Usage
-----
###Get the code:
Fork and clone this repository. Issue pull-requests one document at a time.

### Running Locally (Optional)
------------

### Option 1: Use Vagrant (recommended)
1. Install requirements:
* [virtualBox](https://www.virtualbox.org/wiki/Downloads) >= 4.3.x
* [ansible](http://docs.ansible.com/ansible/intro_installation.html#installing-the-control-machine) >= 1.8.x
* [vagrant-hostmanager](https://github.com/smdahlen/vagrant-hostmanager)
* [vagrant-auto_network](https://github.com/oscar-stack/vagrant-auto_network)
2. From inside the project root, run `vagrant up`
3. You will be prompted for the administration password on your host machine. Obey.
4. Visit <http://docs.local:8000/docs> in your browser of choice.

### Option 2. Install manually
1. Get composer:
 If you do not want to install composer globally, please refer to [getcomposer.org instuctions](https://getcomposer.org/doc/00-intro.md#installation-linux-unix-osx).

 Run the following command to install composer globally:  
 ```
 curl -sS https://getcomposer.org/installer | php
 mv composer.phar /usr/local/bin/composer
 ```

 **Note**: Run the `mv` command with sudo if it fails.  
2. Install dependencies:  
 From within the `documentation` repo, run the following command to install all needed dependencies:  
 ```
 composer install
 ```  
3. Start your local server:  
 If you do not want to install sculpin globally, you can use the following commands to start your local server:  
 ```
 ./vendor/bin/sculpin generate --server
 ```  
 Visit your docs site at: <http://localhost:8000/docs>  

 In order to globally execute sculpin, run the following commands:  
 ```
 curl -O https://download.sculpin.io/sculpin.phar
 sudo chmod +x sculpin.phar
 mv sculpin.phar /usr/local/bin/sculpin
 ```

 Build sculpin and run a local instance:

 ```
 sculpin generate --server
 ```
 Visit your docs site at: <http://localhost:8000/docs>


 Finally, you can tell sculpin to watch the docs directory and automatically
 regenerate anything changed:
 ```
 sculpin generate --server --watch
 ```
 If you use --watch and see it constantly running, regenerating, drop --watch
 until you identify and resolve the problem.  
5. Images  
 For images to render on your local environment you need to apply these commands from within the `documentation` directory:

 ```
 $ cd output_dev
 $ ln -s ./ source
 ```
