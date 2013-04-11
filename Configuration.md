All filters and options are read from ~/.autodl/autodl.cfg. The file will be automatically re-read when changes are made to it when autodl-irssi is running. If you use non-ASCII characters, set the encoding (aka character coding) to UTF-8 before saving.

## Formatting
All lines starting with the # character are ignored as comments. You may use this to disable options.

The file is made up of headers in the form of ``[headername]`` with the options for that header immediately below. The options are in the form of ``option-name = value``. All value options are case-insensitive.

There are different option types:
* Comma separated lists (value1, value2, value3)
* Number lists (1980-1999, 2010, 2012)
* Strings
* Integers
* Booleans (True/False)
* Sizes (120MB, 4.5GB)

The comma separated list type supports wildcards, where ``*`` means 0 or more characters and ``?`` means exactly one character.

## Headers
The different headers are:
* [[Options]] - Global options for autodl-irssi
* [[IRC]] - General IRC configuration for autodl-irssi
* [[Server]] - Settings for tracker IRC servers
* [[Channel]] - Settings for tracker announce channels
* [[Tracker]] - Tracker authentication options
* [[Filter]] - Settings to filter releases for releases
* [[WebUI]] - uTorrent WebUI torrent action settings
* [[FTP]] - FTP torrent action settings