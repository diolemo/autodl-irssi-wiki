## Requirements

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

## Installation

Note: Make sure you're **not** root when you execute the following commands.

	mkdir -p ~/.irssi/scripts/autorun
	cd ~/.irssi/scripts
	wget -O autodl-irssi.zip http://update.autodl-community.com/autodl-irssi-community.zip
	unzip -o autodl-irssi.zip
	rm autodl-irssi.zip
	cp autodl-irssi.pl autorun/
	mkdir -p ~/.autodl
	touch ~/.autodl/autodl.cfg

The autodl-irssi startup script has been copied to the autorun directory so it will be started automatically when Irssi is started.
