### The options header
These options change the behavior of autodl-irssi. Place these options below the **[options]** header.

**Name:** rt-address  
**Type:** string  
**Default:** Whatever is found in ~/.rtorrent.rc  
**Example:** rt-address = 127.0.0.1:5000  
**Description:** If you use the 'rtorrent' action (**upload-method**), then you must initialize this to your rtorrent's SCGI address. It can be ip:port (eg. 127.0.0.1:5000) or /path/to/socket. **NOTE:** This option can only be set in autodl2.cfg, **not** autodl.cfg.


**Name:** update-check  
**Type:** string  
**Default:** ask  
**Example:** update-check = auto  
**Description:** autodl-irssi can auto update itself. Valid values are **ask**, **auto**, and **disabled**. **ask** will print a message when there's a new version. **auto** will automatically update it when there's a new version. **disabled** won't do a thing when there's a new update.

**Name:** max-saved-releases  
**Type:** Integer greater than or equal to 0.  
**Default:** 1000  
**Example:** max-saved-releases = 200  
**Description:** autodl-irssi will remember the last **max-saved-releases** releases you have downloaded so it won't re-download the same file again. Only useful if **save-download-history** is enabled.

**Name:** save-download-history  
**Type:** Boolean  
**Default:** true  
**Example:** save-download-history = true  
**Description:** Set it to false to disable writing the last N (= **max-saved-releases**) downloaded releases to ~/.autodl/DownloadHistory.txt.

**Name:** download-duplicates  
**Type:** Boolean  
**Default:** false  
**Example:** download-duplicates = true  
**Description:** By default, it's false so no duplicate releases are downloaded. Set it to true if you want to download the same release again if it's re-announced.

**Name:** unique-torrent-names  
**Type:** Boolean  
**Default:** false  
**Example:** unique-torrent-names = true  
**Description:** If true, all saved torrent filenames are unique (the site name is prepended to the filename). Set it to false to use the torrent release name as the filename.

**Name:** download-retry-time-seconds  
**Type:** Integer  
**Default:** 300  
**Example:** download-retry-time-seconds = 120  
**Description:** If a download fails, autodl-irssi will try to re-download it after waiting a little while. If it still can't download it after **download-retry-time-seconds** seconds, it will give up and report an error.

**Name:** path-utorrent  
**Type:** String  
**Default:** nothing  
**Example:** path-utorrent = /cygdrive/c/Program Files (x86)/uTorrent/uTorrent.exe  
**Description:** Set it to the path of uTorrent if you're using an **upload-type** equal to **dyndir**.


### Sending Wake on LAN (WOL)
It's possible to wake up the computer before uploading the torrent (uTorrent webui or FTP upload). You may need to make sure your BIOS and network card have WOL enabled.

wol-mac-address = 00:11:22:33:44:55
wol-ip-address = 12.34.56.78  (or a DNS name, eg. www.blah.com)
wol-port = 9 (defaults to 9 if you leave it blank)

**wol-mac-address** is the MAC (or hardware) address of the computer's network card. Use ifconfig /all (windows) or ifconfig -a (Linux) to find out your network card's MAC address.

If you have a router, then set **wol-ip-address** to your router's public IP address, and make sure the router forwards UDP packets to port **wol-port** (default 9) to your router's internal broadcast address (usually 192.168.0.255).


### Torrent action options
autodl-irssi can save a torrent file to a watch directory, upload it to uTorrent webui, upload it to an FTP server, execute a program or use uTorrent to save it to a dynamic directory name that depends on the current torrent.

There's a global action option in the [options] header and a local action option in each filter. By default, the global action option is used but you can override it in any filter by placing a new **upload-type** below your [filter] header.

**rtorrent only:**
	upload-type = rtorrent
	rt-dir = /home/YOURNAME/downloads/$(Month)$(Day)/$(Tracker)
	rt-commands = print="Added: $(TorrentName)"; print="Hello, world!"
	rt-label = $(Tracker)
	#rt-ratio-group = rat_3
	#rt-channel = thr_2
	rt-priority = high
	#rt-ignore-scheduler = true
	#rt-dont-add-name = false

**rt-dir** is the destination directory. The torrent data will be saved here. Macros can be used.  
**rt-commands** can be used to execute some rtorrent commands when loading the torrent file. It's for advanced users only.  
**rt-label** is used to set a ruTorrent label.  
**rt-ratio-group** is used to set a ruTorrent ratio group. Valid names are rat_0, rat_1, ..., rat_7. You must have the ratio ruTorrent plugin installed.  
**rt-channel** is used to set a ruTorrent channel. Valid names are thr_0, thr_1, ..., thr_9. You must have the throttle ruTorrent plugin installed.  
**rt-priority** sets the torrent priority. Valid values are 0, dont-download, 1, low, 2, normal, 3, high. If you set it to dont-download (or 0), the torrent is loaded, but not started.  
**rt-ignore-scheduler**: set it to true to disable the ruTorrent scheduler.  
**rt-dont-add-name**: set it to true if you don't want the torrent name to be added to the path.  


**Save torrent to a watch directory:**
	upload-type = watchdir
	upload-watch-dir = /home/myusername/mywatchdir

**Upload torrent to uTorrent webui:**
Don't forget to initialize webui user, password, etc below the [webui] header!
	upload-type = webui

**Upload torrent to an FTP server:**
Don't forget to initialize FTP user, password, etc below the [ftp] header!
```
upload-type = ftp
upload-ftp-path = /ftp/server/path
```
**Execute a program:**
```
upload-type = exec
upload-command = /path/to/program
upload-args = all arguments here
```
Both **upload-command** and **upload-args** support macros. See Macros below for an explanation of all available macros. Just remember to enclose the macro in double quotes if it's possible that the macro contains spaces. Example: **upload-args = --torrent "$(TorrentPathName)" --category $(Category)**


**Save torrent data to a dynamic directory using uTorrent:**
You need to initialize **path-utorrent** below [options] or it won't work!

	upload-type = dyndir
	upload-dyndir = c:\the\windows\path\$(macro)$(macro2)\$(macro3)

Important: autodl-irssi assumes that the Z: drive is mapped to your / (root) directory if you're using Wine to run uTorrent.

**upload-dyndir** supports macros. See Macros below for an explanation of all available macros. You can use macros to create a directory based on current day and month. Some examples:

**upload-dyndir = c:\mydownloads\$(year)-$(month)-$(day)** will save the torrent data below a directory containing the current year, month and day. Eg. **c:\mydownloads\2010-10-28** if 2010-10-28 happened to be the current day.

**upload-dyndir = c:\mydownloads\$(month)$(day)\$(trackershort)\$(category)** will save the data to a directory based on current month, day, tracker name, and torrent category.