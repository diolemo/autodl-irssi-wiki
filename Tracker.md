### The tracker header
Your trackers require that you authenticate before letting you download a torrent file. Use the tracker headers to set the required options so downloads work.

A tracker header looks like **[tracker TYPE]** where **TYPE** is the tracker type. This is the exact same type that you find in the **~/.irssi/scripts/AutodlIrssi/trackers/*.tracker** files. Open one of the files with a text editor and locate the **type="XYZ"** line. Use the value inside the quotes, eg. **XYZ**. Example: **[tracker XYZ]**. Case matters so XYZ is different from xyz.

Some trackers require a **passkey**, others an **authkey**, or a **cookie**, etc. To quickly find out which one your tracker needs, just add **[tracker TYPE]** (with no options below it) to autodl.cfg and wait 1-2 seconds (start Irssi if necessary). It will report the missing options, eg.: **ERROR: /home/YOURNAME/.autodl/autodl.cfg: line 123: TRACKER-TYPE: Missing option(s): passkey, uid**. Here it's saying that you forgot to add the options **passkey = XXX** and **uid = YYY**. Add them below the tracker header.

Some common tracker options and how to get them:

**cookie**: Go to your tracker's home page, then type **javascript:document.innerHTML=document.cookie** in the address bar and press enter. You should now see your cookie. If all you see is PHPSESSID=XXXXX, then you'll have to manually get the cookie using FireFox: Edit -> Preferences -> Privacy tab -> Show Cookies. It's usually just **uid=XXX; pass=YYY**. Separate each key=value pair with a semicolon.

**passkey**: First check a torrent download link if it contains it. If not you can usually find it in the generated RSS-feed URL, which you probably can generate @ yourtracker.com/getrss.php . passkeys are usually exactly 32 characters long. The passkey can also sometimes be found in your profile (click your name).

**authkey**: See **passkey** above. For gazelle sites, it's part of the torrent download link.

**torrent_pass**: For gazelle sites, it's part of the torrent download link.

**uid**: Click your username and you should see the id=XXX in the address bar. That's your user id, or uid.

	[tracker TYPE]
	#enabled =
	#force-ssl =
	#upload-delay-secs =
	#cookie =
	#passkey =
	#etc ...

**enabled** is optional and defaults to true. Set it to false to disable the tracker.  
**force-ssl** is optional and can be set to true to force encrypted torrent downloads. Not all trackers support HTTPS downloads. Leave it blank for the default value (which is HTTP or HTTPS).  
**upload-delay-secs** is optional and is the number of seconds autodl-irssi should wait before uploading/saving the torrent. Default is 0 (no wait). This option isn't needed 99.999% of the time.