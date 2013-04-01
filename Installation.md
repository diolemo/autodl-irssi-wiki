The install script will install autodl-irssi and optionally also ruTorrent, the ruTorrent plugin and any other dependencies required to have a fully working ruTorrent install. It will ask a few questions and then install whatever you selected.

### Ubuntu and Ubuntu clones

	cd
	wget --no-check-certificate -O autodl-setup https://github.com/downloads/autodl-irssi-community/autodl-irssi/autodl-setup
	sudo sh autodl-setup

### Any other OS
Log in as root:
	su -
Then install it:

	wget --no-check-certificate -O autodl-setup https://github.com/downloads/autodl-irssi-community/autodl-irssi/autodl-setup
	sh autodl-setup


To use the autodl-irssi ruTorrent plugin, click its icon at the top of ruTorrent. It's usually the icon to the left of ruTorrent's settings icon. The icon is either a white bubble or a white down arrow inside a green square. The autodl-irssi tab will show all autodl-irssi output as long as ruTorrent is loaded.



If you don't use the ruTorrent plugin, then you may want to send all autodl-irssi output to its own window:
By default, all autodl-irssi output goes to the **(status)** window. If there's a window called **autodl**, then it will write all output to that window. Use these Irssi commands to create a new window named **autodl** and place it right after the status window (i.e., window position 2)

	First start Irssi! :D
	/window new hidden
	/window name autodl
	/window move 2
	/layout save
	/save


Since some people don't want users to have shell access, it's also possible to disable the "exec" action. Create **/etc/autodl.cfg** and add this:

	[options]
	allowed = watchdir, rtorrent

That will only enable the rtorrent and "Save to watch dir" actions. The following can be used with the **allowed** option:

rtorrent
watchdir
webui (requires uTorrent)
ftp
exec
dyndir (requires uTorrent)

It's a comma seperated list, eg.: allowed = watchdir, ftp



## Manual installation

If you can't use the installer for some reason, then try a manual install.

autodl-irssi requires Irssi compiled with Perl support.

autodl-irssi has the following Perl module dependencies:
* Archive::Zip
* Net::SSLeay
* HTML::Entities
* XML::LibXML
* Digest::SHA1
* JSON
* JSON::XS (optional)

Use your package manager to install them or use the CPAN utility. If you use CPAN, you will need a build environment already installed, eg. gcc, make, etc.

	cpan Archive::Zip Net::SSLeay HTML::Entities XML::LibXML Digest::SHA1 JSON JSON::XS

The optional ruTorrent plugin has the following PHP dependencies:
* json
* sockets
* xml

You can test for the presence of those modules by executing the following command. If you get no output then they're installed:

	for module in json xml sockets; do php -m|grep -wq $module || echo "Missing module: $module"; done

Use your package manager to install them unless they're already installed. You may need to edit your php.ini file by adding this:

	extension=sockets.so
	extension=json.so
	extension=xml.so


Don't forget to restart your web server if you make any changes to php.ini.


Installing autodl-irssi. Note: Make sure you're **not** root when you execute the following commands.

	mkdir -p ~/.irssi/scripts/autorun
	cd ~/.irssi/scripts
	wget -O autodl-irssi.zip https://autodl-irssi-community.googlecode.com/files/autodl-irssi-community-v1.34.zip
	unzip -o autodl-irssi.zip
	rm autodl-irssi.zip
	cp autodl-irssi.pl autorun/
	mkdir -p ~/.autodl
	touch ~/.autodl/autodl.cfg


The autodl-irssi startup script has been copied to the autorun directory so it will be started automatically when Irssi is started.


Installing the optional ruTorrent plugin. You may need to slightly modify the steps if you're not using Ubuntu or if ruTorrent isn't installed to /var/www/rutorrent/

	cd /var/www/rutorrent/plugins
	sudo svn co https://autodl-irssi.svn.sourceforge.net/svnroot/autodl-irssi/trunk/rutorrent/autodl-irssi
	sudo cp autodl-irssi/_conf.php autodl-irssi/conf.php
	sudo chown -R www-data:www-data autodl-irssi


This install assumes ruTorrent is not password protected. For password protected (i.e., multi-user) setup, you need to copy conf.php to the user plugins directory and not to the plugin directory. Eg. you need to copy it to a path similar to /var/www/rutorrent/conf/users/YOUR-USER-NAME/plugins/autodl-irssi

Edit conf.php with a text editor and add your port number and password. The port number should be a random number between 1024 and 65535 inclusive. The file should look something like this afterwards:

	<?php
	$autodlPort = 12345;
	$autodlPassword = "secretpass";
	?>


Open ~/.autodl/autodl2.cfg with a text editor and add this to the file:

```
[options]
gui-server-port = 12345
gui-server-password = secretpass
```

If you start more than one Irssi process, make sure each Irssi process uses a unique port number! It won't work if they all use the same port number.