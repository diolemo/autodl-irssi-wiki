**output-level = 5**
```
AnnounceParser.pm:537 - Full release variable output
Exec.pm:69 - "Forked. pid: $pid, exec: '$program'"
FtpClient.pm:191 - "FTP: $self->{codeMessage}"
FtpClient.pm:212 - "FTP: PASS ****"
FtpClient.pm:215 - "FTP: $line"
Startup.pm:473 - "Checking for updates..."
Startup.pm:483 - "Downloaded update.xml"
Updater.pm:566 - "Creating file '$info->{destFile}'"
Updater.pm:282 - "Extracting file '$info->{destFile}'"
UtorrentWebUI:413 - "Got new \x{03BC}Torrent webui token: $AutodlIrssi::g->{options}{webuiToken}, cookies: " . $AutodlIrssi::g->{options}{webuiCookies}->toString()
```

**output-level = 5; debug = true**
```
ActiveConnections.pm:66 - "Added connection: id: $id, class: $info->{class}, name: '$info->{name}'"
ActiveConnections.pm:83 - "Removed connection: id: $id"
HttpRequest:208 - "Trying to connect: url: $self->{url}")
HttpRequest:223 - "Failed to connect: url: $self->{url}"
HttpRequest:228 - "Now connected: url: $self->{url}"
HttpRequest:253 - "Sending HTTP headers:\n" . substr($msg, 0, 700)
HttpRequest:268 - "Failed to send HTTP request: url: $self->{url}"
HttpRequest:358 - "HTTP response headers:\n" . substr($self->{data}, 0, $endOfHeader + 2)
HttpRequest:359 - "HTTP data:\n" . substr($self->{data}, $endOfHeader + 4, 700)
MatchedRelease.pm:599 - "Dest dir: '$rtDir'"
MatchedRelease.pm:618 - "rtorrent commands: '$cmds'"
Scgi.pm:106 - "Connecting to $self->{addr}"
Scgi.pm:128 - "Failed to connect!"
Scgi.pm:132 - "Connected. Now sending data."
Scgi.pm:146 - "Failed to send SCGI request"
Scgi.pm:153 - "Error reading data: $errorMessage"
```

**output-level = 4**
```
AutoConnector.pm:578 - "Failed to set nick!"
AutoConnector.pm:594 - "Got new nick: '$newNick'"
AutoConnector.pm:630 - "Sending NICK command"
AutoConnector.pm:643 - "Sending GHOST command"
AutoConnector.pm:675 - "GHOST nick is not in use."
AutoConnector.pm:714 - "Sending IDENTIFY command"
AutoConnector.pm:762 - "Your nick has already been identified!"
AutoConnector.pm:829 - "Sending REGISTER command"
AutoConnector.pm:873 - "Can't register nick yet. Must wait."
AutoConnector.pm:952 - "$channelInfo->{name}: Sending invite command: $inviteCommand"
AutoConnector.pm:979 - "$channelInfo->{name}: Sending join command: join $command"
AutoConnector.pm:1025 - "$channelInfo->{name}: Sending HTTP invite command"
AutoConnector.pm:1079 - "Trying to set nick again"
GuiServer.pm:272 - "GuiServer: Error getting JSON data: $errorMessage"
HttpRequest:198 - "Retrying request ($self->{retryCount}) $self->{url}, error was: $self->{retryErrorMessage}
MatchedRelease.pm:101 - "Release \x02\x0309$self->{ti}{torrentName}\x03\x02 (\x02\x0302$self->{trackerInfo}{longName}\x03\x02) has already been downloaded"
MatchedRelease.pm:363 - "Torrent '$self->{ti}{torrentName}' ($self->{trackerInfo}{longName}): Starting webui upload."
MatchedRelease.pm:402 - "Torrent '$self->{ti}{torrentName}' ($self->{trackerInfo}{longName}): Starting ftp upload."
Startup.pm:527 - "Updating tracker files..."
TempFiles.pm:79 - "Deleted temporary file '$fileInfo->{pathname}'"
TrackerLogChecker.pm:137 - "Checking directory $_"
TrackerLogChecker.pm:153 - "Checking file $file"
```

**output-level = 4; debug = true**
```
Startup.pm:552 - "Trackers updated"
```

**output-level = 3** (default)
```
AutoConnector.pm:223 - "Connection settings changed. Reconnecting!"
AutoConnector.pm:586 - "Got invited to $channelName"
AutoConnector.pm:678 - "Killed ghost connection!"
AutoConnector.pm:766 - "Identified nick!"
AutoConnector.pm:882 - "Registered nick! NickServ reply:\n" . join("\n", @$lines)
AutoConnector.pm:1055 - "$channelInfo->{name}: HTTP invite request sent successfully."
AutoConnector.pm:1092 - "Retrying " . NICKSERV_NICK . " IDENTIFY command"
AutoConnector.pm:1416 - "Disconnecting dupe IRC server: $name"
ChannelMonitor.pm:193 - "$serverName: Monitoring channel $channelName"
GuiServer.pm:226 - "GUI server listening on $address:$port"
GuiServer.pm:229 - "GUI server is disabled"
GuiServer.pm:242 - "GUI server disabled. Got error: $errorMessage"
MatchedRelease.pm:169 - "Matched " . $self->_getTorrentInfoString()
MatchedRelease.pm:245 - _getTorrentInfoString . " is too big/small, size: \x02" . convertToByteSizeString($self->{ti}{torrentSizeInBytes}) . "\x02. Not downloaded.";
MatchedRelease.pm:266 - "Waiting $uploadDelaySecs seconds. Torrent " . _getTorrentInfoString
MatchedRelease.pm:319 - "Sending WOL: MAC=$filter->{wolMacAddress}, IP=$destIpAddr, Port=$filter->{wolPort}"
MatchedRelease.pm:672 - "$startMsg " . _getTorrentInfoString . ", total time \x02\x0313$totalTime\x03\x02 seconds"
Startup.pm:78 - "\x02autodl-irssi\x02 \x02v$version\x02 is now enabled! :-)"
Startup.pm:79 - "\x02\x0309Bugs and Requests\x03\x02 \x02https://github.com/autodl-community/autodl-irssi/issues/\x02"
Startup.pm:119 - "\x02autodl-irssi\x02 \x02v$version\x02 is now disabled! ;-("
Startup.pm":216 - "Tracker options ($type):" (/autodl dumpvars output)
Startup.pm:232 - "Loaded \x02" . $numLoaded . "\x02 release" . ($numLoaded == 1 ? "" : "s") . " from history file."
Startup.pm:303 - "Reading configuration files"
Startup.pm:490 - "\x0309You are using the latest version!\x03"
Startup.pm:498 - "\x0309A new version is available!\x03 Type \x02/autodl update\x02 to update or \x02/autodl whatsnew\x02."
Startup.pm:504 - "\x0309You are using the latest version!\x03"
Startup.pm:507 - "New:\n" . $updater->getAutodlWhatsNew()
Startup.pm:520 - "Downloading update...";
Startup.pm:543 - "Reloading autodl-irssi..."
TrackerLogChecker.pm:93 - "Verifying tracker $trackerInfo->{longName} ($trackerInfo->{type})"
TrackerLogChecker.pm:113 - "\x0300,03 Done \x03; No errors; Checked $self->{numAnnounceLines} lines; tracker $trackerInfo->{longName} ($trackerInfo->{type})"
TrackerLogChecker.pmp:142 - "No channels directory: $dir"
TrackerManager.pm:135 - "\x02Added tracker\x02 \x0309" . $announceParser->getTrackerName() . "\x03"
TrackerManager.pm:139 - "\x02Removed tracker\x02 \x0304" . $announceParser->getTrackerName() . "\x03"
TrackerManager.pm:159 - "\x0304WARNING\x03: \x02$trackerInfo->{longName}\x02: Nothing announced since " . localtime($trackerState->{lastAnnounce})
Updater.pm:386 - "The following Perl module(s) are required, but missing:"
Updater.pm:387 - "    \x0309@{$self->{missingModules}}\x03"
Updater.pm:388 - "Execute one of these commands as the \x02root user\x02 to install them:"
Updater.pm:391 - "\x0303$info->{os}\x03:"
Updater.pm:401 - "    \x0308$command\x03"
```

**output-level = 3; debug = true**


**output-level = 2**


**output-level = 2; debug = true**


**output-level = 1**


**output-level = 1; debug = true**


**output-level = 0**
```
ActiveConnections.pm:78 - "ActiveConnections: Could not find id $id"
ActiveConnections.pm:92 - "Memory leak: id: $id, class: $info->{class}, name: '$info->{name}'"
AnnounceParser.pm:227 - "Got exception in onNewLine: " . formatException($@)
AnnounceParser.pm:295 - $self->getTrackerName() . ": invalid extractInfo.vars.length"
AnnounceParser.pm:360 - "extract: Did not match regex: " . $obj->{extract}{regexInfo}{regex} . ", varName: '" . $obj->{extract}{srcvar} . "'"
AnnounceParser.pm:372 - "extractone: Did not match any regex."
AutoConnector.pm:71 - "notifyAll: ex: $@"
AutoConnector.pm:396 - "Timer handler: $@"
AutoConnector.pm:458 - "_onWaitNickServReply: $@"
AutoConnector.pm:486 - "_onWaitNickServReply: $@"
AutoConnector.pm:692 - "_ghostReply: $@"
AutoConnector.pm:770 - "Invalid nick password!"
AutoConnector.pm:774 - "IDENTIFY: Nick isn't registered!"
AutoConnector.pm:788 - "Failed to IDENTIFY nick."
AutoConnector.pm:793 - "Can't IDENTIFY nick. You must complete the registration by reading your email."
AutoConnector.pm:796 - "IDENTIFY: Got unknown code '$code'"
AutoConnector.pm:804 - "_identifyReply: $@"
AutoConnector.pm:817 - "Could not register nick: missing email address"
AutoConnector.pm:840 - "Sent REGISTER command. Got no reply from NickServ."
AutoConnector.pm:864 - "Got unknown REGISTER response:\n" . join("\n", @$lines)
AutoConnector.pm:869 - "Could not register nick. Timed out!"
AutoConnector.pm:886 - "Can't register nick! It's already been registered!"
AutoConnector.pm:889 - "Nick REGISTER reply:\n" . join("\n", @$lines)
AutoConnector.pm:892 - "REGISTER: Got unknown code '$code'"
AutoConnector.pm:901 - "_registerReply: $@"
AutoConnector.pm:1001 - "$channelInfo->{name}: HTTP invite request failed. Stuck connection."
AutoConnector.pm:1040 - "$channelInfo->{name}: HTTP invite request failed. Retrying later. Error: $errorMessage"
AutoConnector.pm:1050 - "$channelInfo->{name}: HTTP invite request failed. Not retrying. Error: $statusText"
AutoConnector.pm:1060 - "$channelInfo->{name}: HTTP invite request failed. Retrying later. Error: $statusText"
AutoConnector.pm:1075 - "Could not set nick. Reconnecting..."
AutoConnector.pm:1108 - "_checkState: $@"
AutoConnector.pm:1294 - "_onMessageFullyConnected: ex: $@"
AutoConnector.pm:1323 - "_onMessageDisconnect: ex: $@"
AutoConnector.pm:1337 - "_onMessageNotice: ex: $@"
AutoConnector.pm:1356 - "_onMessageNick: ex: $@"
AutoConnector.pm:1385 - "_onMessageInvite: ex: $@"
AutoConnector.pm:1403 - "_checkServerState: $@"
BitTorrent.pm:79 - "Caught an exception in getTorrentFiles(): " . formatException($@)
ChannelMonitor.pm:125 - "_onMessageDisconnect: ex: $@"
ChannelMonitor.pm:142 - "_onMessageJoin: ex: $@"
ChannelMonitor.pm:159 - "_onMessagePart: ex: $@"
ChannelMonitor.pm:176 - "_onMessageKick: ex: $@"
ChannelMonitor.pm:185 - "$serverName: Not monitoring channel $channelName"
ConfigFileParser:101 - "$self->{pathname}: line $lineNumber: $msg"
DownloadHistory.pm:66 - "Could not open '$self->{filename}' for writing: $!"
DownloadHistory.pm:124 - "Could not open '$self->{filename}' for writing: $!"
EventManager.pm:50 - "Event '$eventInfo->{event}' was not unregistered"
EventManager.pm:86 - "EventManager: invalid handler id ($handlerId) for event '$event'"
EventManager.pm:109 - "EventManger: $eventInfo->{event}: handler error. ex: $@"
FtpClient.pm:667 - "FtpClient.sendCommandsCompleted: ex: " . formatException($@)
GuiServer.pm:88 - "JsonSocket: timeout: ex: $@"
GuiServer.pm:140 - "JsonSocket: ex: $@"
GuiServer.pm:232 - "gui-server-password is blank or missing. All requests will be blocked!"
GuiServer.pm:299 - "GuiServer: could not send data: $errorMessage"
HttpRequest.pm:111 - "HttpRequest::_callUser: $@"
IrcHandler.pm:100 - "Exception in onPrivmsg: " . formatException($@)
MatchedRelease.pm:165 - "Can't download \x02\x0309$self->{ti}->{torrentName}\x03\x02. Initialize \x02\x0304$missingStr\x03\x02 below \x02\x0306[tracker $trackerType]\x03\x02 in \x02\x0307$autodlPath\x03\x02 (ruT: Trackers dialog box)"
MatchedRelease.pm:202 - "Error downloading torrent file $self->{downloadUrl}. Error: $errorMessage"
MatchedRelease.pm:208 - "Got HTTP $statusCode, check your cookie settings! Torrent: $self->{ti}{torrentName}, tracker: $self->{trackerInfo}{longName}"
MatchedRelease.pm:233 - "Could not parse torrent file '$self->{ti}{torrentName}'"
MatchedRelease.pm:284 - "Can't save/upload torrent: Torrent action '$method' is disabled!"
MatchedRelease.pm:306 - "Upload type not implemented, type: $self->{uploadMethod}{uploadType}"
MatchedRelease.pm:324 - "Could not send WOL: $@"
MatchedRelease.pm:349 - "Could not save torrent file; error: " . formatException($@)
MatchedRelease.pm:372 - "Could not send '$self->{ti}{torrentName}' to webui; error: " . formatException($@)
MatchedRelease.pm:381 - "Could not send '$self->{ti}{torrentName}' to uTorrent (webui): error: $errorMessage"
MatchedRelease.pm:385 - "Error adding torrent: " . $commandResults->[0]{json}{error}
MatchedRelease.pm:422 - "Could not upload '$self->{ti}{torrentName}' to ftp; error: " . formatException($@)
MatchedRelease.pm:431 - "Could not upload '$self->{ti}{torrentName}' to ftp: error: $errorString"
MatchedRelease.pm:491 - "Could not start program, torrent '$self->{ti}{torrentName}', error: " . formatException($@)
MatchedRelease.pm:520 - "Missing path-utorrent = XXX below [options]. Can't start uTorrent. Torrent: $self->{ti}{torrentName}"
MatchedRelease.pm:532 - "Wine is missing. Can't run uTorrent. Path to wine should be $command"
MatchedRelease.pm:543 - "Could not start uTorrent, torrent '$self->{ti}{torrentName}', error: " . formatException($@)
MatchedRelease.pm:580 - "Can't send torrent file to rtorrent. You have not initialized rt-address (SCGI address)."
MatchedRelease.pm:635 - "Could not send rtorrent commands, torrent '$self->{ti}{torrentName}', error: " . formatException($@)
MatchedRelease.pm:644 - "Could not send '$self->{ti}{torrentName}' to rtorrent: error: $errorMessage"
MessageBuffer.pm:99 - "MessageBuffer::secondTimer: ex: $@"
Scgi.pm:72 - "Scgi::_callUser: ex: $@"
ServerSocket.pm:85 - "Server socket: Error: $error"
ServerSocket.pm:107 - "Server socket: Error: $@"
SocketBase.pm:210 - "Socket: callback ex: $@"
SocketBase.pm:228 - "_callUserShutdown: ex: $@"
Startup.pm:83 - "Missing configuration file: " . getAutodlCfgFile()
Startup.pm:143 - "disable: ex: $@"
Startup.pm:160 - "Could not read AutodlState.xml: ex: $@"
Startup.pm:177 - Startup.pm:160 - "Could not read AutodlState.xml: ex: $@"
Startup.pm:203 - "command_autodl: ex: $@"
Startup.pm:212 - "Unknown tracker type $type"
Startup.pm:241 - "Error when reading tracker files: " . formatException($@)
Startup.pm:348 - "Error when reading the config file: $@"
Startup.pm:363 - "secondTimer: ex: " . formatException($@)
Startup.pm:389 - "reportBrokenAnnouncers: ex: $@"
Startup.pm:429 - "checkForUpdates: ex: $@"
Startup.pm:440 - "manualCheckForUpdates: ex: $@"
Startup.pm:451 - "manualCheckForUpdates: ex: $@"
Startup.pm:458 - "Could not check for updates: $errorMessage"
TempFiles.pm:76 - "Could not delete temporary file '$fileInfo->{pathname}'"
TrackerLogChecker.pm:88 - "Could not find tracker with type: $trackerType"
TrackerLogChecker.pm:106 - "Tracker: $trackerInfo->{longName}: Got an exception: " . formatException($@)
TrackerLogChecker.pm:110 - "\x0300,04 Done \x03; ERRORS: $self->{numErrors}; Checked $self->{numAnnounceLines} lines; tracker $trackerInfo->{longName} ($trackerInfo->{type})"
TrackerManager.pm:88 - "Could not parse '$filename': Error: $@"
TrackerManager.pm:109 - "Tracker with type '$type' has already been added."
Updater.pm:90 - "Updater::_notifyHandler: ex: $@"
UtorrentWebui.pm:436 - "UtorrentWebui.sendCommandsCompleted: ex: " . formatException($@)
XmlRpc:71 - "XmlRpc::_callUser: ex: $@"
```

**output-level = 0; debug = true**
```
AnnounceParser.pm:250 - $self->getTrackerName() . ": did not match line '$line'"
AnnounceParser.pm:269 - $self->getTrackerName() . ": did not match line '$line'"
AutoConnector.pm:259 - "Could not disconnect. Server not found."
AutoConnector.pm:605 - "hasCorrectNick: server is undef"
AutoConnector.pm:657 - "Sent GHOST command. Got no reply from NickServ."
AutoConnector.pm:672 - "Got unknown GHOST response:\n" . join("\n", @$lines)
AutoConnector.pm:726 - "Sent IDENTIFY command. Got no reply from NickServ."
AutoConnector.pm:758 - "Got unknown IDENTIFY response:\n" . join("\n", @$lines)
GuiServer.pm:82 - "JsonSocket: Aborting, timed out!"
Startup.pm:228 - "Error when reading download history file: " . formatException($@)
```
