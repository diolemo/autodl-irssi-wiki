**output-level = 5**
```
AnnounceParser.pm:537 - Full release variable output
```

**output-level = 5; debug = true**
```
ActiveConnections.pm:66 - "Added connection: id: $id, class: $info->{class}, name: '$info->{name}'"
ActiveConnections.pm:83 - "Removed connection: id: $id"
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
```

**output-level = 4; debug = true**


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
```
