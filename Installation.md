## Automatic Installation

We no longer maintain copy of the autodl-setup seedbox setup script. Here are some alternatives:

* [SeedboxCreationScript](https://github.com/SeedboxCreator/SeedboxCreationScript)

## Manual Installation

If you can't use the installer for some reason, then try a manual install.

autodl-irssi requires irssi compiled with Perl support.

autodl-irssi has the following Perl module dependencies:
* Archive::Zip
* Net::SSLeay
* HTML::Entities
* XML::LibXML
* Digest::SHA
* JSON
* JSON::XS (optional)

Use your package manager to install them or use the CPAN utility. If you use CPAN, you will need a build environment already installed, eg. gcc, make, etc.

	cpan Archive::Zip Net::SSLeay HTML::Entities XML::LibXML Digest::SHA JSON JSON::XS

Installing autodl-irssi. Note: Make sure you're **not** root when you execute the following commands.

	mkdir -p ~/.irssi/scripts/autorun
	cd ~/.irssi/scripts
	wget -O autodl-irssi.zip https://autodl-irssi-community.googlecode.com/files/autodl-irssi-community.zip
	unzip -o autodl-irssi.zip
	rm autodl-irssi.zip
	cp autodl-irssi.pl autorun/
	mkdir -p ~/.autodl
	touch ~/.autodl/autodl.cfg

The autodl-irssi startup script has been copied to the autorun directory so it will be started automatically when Irssi is started.

## Post-Installation

### ruTorrent

If you want to install the ruTorrent plugin, see the instructions [here](https://github.com/autodl-community/autodl-rutorrent/wiki)

### autodl Window

By default, all autodl-irssi output goes to the **(status)** window. If you want to send all autodl-irssi output to its own window, you can create a window in irssi named **autodl**. Use these irssi commands to create a new window named **autodl** and place it right after the status window (i.e., window position 2)

	First start Irssi! :D
	/window new hidden
	/window name autodl
	/window move 2
	/layout save
	/save
