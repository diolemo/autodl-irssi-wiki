# Installation of autodl-irssi-community on Wheezy

These are some instructions and notes on installing autodl-irssi on Debian Wheezy.  My installation of Debian 7 was minimal and only included an openssh-server and system utilities.

## Assumptions
I am assuming a few things here.

1. That you have a working Debian 7 system
2. You have administrative access to your system
3. You already have a web server serving up php scripts and specifically rutorrent
4. Perl is already installed on your system and functional

## Install

### Irssi

Considering the name of this project, the first thing we should do is install irssi.  **Please note that these commands should be run as root or prefixed with sudo.**
`aptitude update && aptitude install -y irssi`

### Dependencies
We need to install some perl dependencies that are required for the script to run

````
aptitude install -y libarchive-zip-perl libnet-ssleay-perl libhtml-parser-perl \
libxml-libxml-perl libjson-perl libjson-xs-perl libxml-libxslt-perl
````
libdigest-sha1-perl has been deprecated in Debian.  For now we will use cpan to install this module.

`cpan Digest::SHA1`

(if cpan asks you questions you should just be able to use the defaults by pressing enter a few times)

### Autodl-irssi
Now we can install autodl-irssi-community into irssi, as well as setting it up to start automatically with irssi. **These commands should be run as the user you will be using autodl-irssi with**, **_Make sure you have unzip installed_**

````
mkdir -p ~/.irssi/scripts/autorun
cd ~/.irssi/scripts
wget -O autodl-irssi.zip https://autodl-irssi-community.googlecode.com/files/autodl-irssi-community-v1.34.zip
unzip -o autodl-irssi.zip
rm autodl-irssi.zip
ln -s ../autodl-irssi.pl autorun/
mkdir -p ~/.autodl
touch ~/.autodl/autodl.cfg
````

### Optional Rutorrent Plugin

#### PHP Modules Check 
The plugin requires a few PHP modules for the rutorrent plugin.  My system had these installed by default. _If you have php5-cli installed_, you can run `for module in json xml sockets; do php -m|grep -wq $module || echo "Missing module: $module"; done`.  This will tell you if you are missing any modules.

#### Plugin install
Assuming you installed rutorrent under /var/www/rutorrent, you can do the following to install the plugin.  **Depending on your configuration these commands likely need to be run as root or sudo**

````
cd /var/www/rutorrent/plugins
svn co https://autodl-irssi.svn.sourceforge.net/svnroot/autodl-irssi/trunk/rutorrent/autodl-irssi
cp autodl-irssi/_conf.php autodl-irssi/conf.php
chown -R www-data:www-data autodl-irssi
````

#### Plugin setup
You will need to customize the configuration files for the plugin as well as autodl-irssi.

Edit `/var/www/rutorrent/plugins/autodl-irssi/conf.php` with your own Port and Password. **Replace 12345 and secretpass with your own settings**

````
<?php
$autodlPort = 12345;
$autodlPassword = "secretpass";
?>
````

Now edit `~/.autodl/autodl.cfg` (or add ~/.autodl/autodl2.cfg) to have the same port and password

````
[options]
gui-server-port = 12345
gui-server-password = secretpass
````

_Note: You need quotation marks in the php file, but not the cfg file for password._

### Done!
At this point you should be able to start irssi, and the plugin should be functional in your rutorrent instance.

### Configuration
For advanced configuration please refer to [this page](https://github.com/autodl-irssi-community/autodl-irssi/wiki/Configuration)