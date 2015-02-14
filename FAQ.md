### How do I get a new tracker added to autodl-irssi?
If you know how to create a new tracker file or edit an existing tracker file to suit your needs, you can submit a Pull Request to the [trackers repository](https://github.com/autodl-community/autodl-trackers) following the [contributing guidelines](https://github.com/autodl-community/autodl-trackers/blob/master/CONTRIBUTING.md#submitting-code). If you need it to be created by a member of autodl-community, [submit an issue](https://github.com/autodl-community/autodl-trackers/blob/master/CONTRIBUTING.md#submitting-an-issue) to the [trackers repository](https://github.com/autodl-community/autodl-trackers) or come to the IRC channel in the footer with the following information:

* Tracker name
* Tracker abbreviation (if applicable)
* Tracker IRC server address
* Tracker IRC announce channel
* Tracker IRC announcer name
* A decent size sampling of announces from the announce channel (at least 5-10)

Preferably, this information should be provided using a pastebin site.

### I'm getting this error: "Error downloading files. Make sure autodl-irssi is started and configured properly (eg. password, port number): Error getting files listing: Error: Could not connect: (111) Connection refused". How do I fix this?
This is an error that occurs in the ruTorrent plugin when it can't communicate with autodl-irssi. This could be for a number of reasons:

* irssi may not be running
* autodl-irssi may not be enabled in irssi
* multiple instances of irssi with autodl-irssi enabled could be running
* your gui-server and gui-server-password settings may not be set in your autodl.cfg file
* your gui-server and gui-server-password settings may not be set in the ruTorrent plugin's conf.php
* the gui-server and gui-server-password settings in your autodl.cfg may not match the settings in the ruTorrent plugin's conf.php
* you may be using a seedbox from Feral Hosting; follow [their instructions](https://www.feralhosting.com/faq/view?question=142) to get it working

