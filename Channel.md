```
[channel irc.server.com]
name = 
password = 
invite-command = 
invite-http-url = 
invite-http-header = 
invite-http-data = 
```

Create one **[channel]** header per server.

**name:** The name of the channel to join.  
**password:** The password for the channel. Don't set if the channel is not password-protected.  
**invite-command:** An IRC command to be invited into the channel.  
**invite-http-url, invite-http-header, invite-http-data:** Used if the channel requires an http invite.