Create one [filter] header per filter. You can optionally name the filter like **[filter MY FILTER NAME]**. All filter options are optional! If you don't use any filter options, then everything will be downloaded because your filter doesn't filter out anything.

**enabled**
> **Type:** Boolean  
**Default:** true  
**Example:** enabled = false  
**Description:** Use it to disable a filter. All filters are enabled by default.

**match-releases**
> **Type:** Comma separated list  
**Example:** match-releases = The?Simpsons*, American?Dad*  
**Description:** It's compared against the torrent name, eg. **Some.release.720p.HDTV-GROUP**. If the filter should only match TV-shows or movies, it's easier to use the **shows** filter option since it doesn't require wildcards.

**except-releases**
> **Description:** The exact opposite of **match-releases**. If a release matches this option, then it's NOT downloaded.

**match-categories**
> **Type:** Comma separated list  
**Example:** match-categories = *MP3*, TV/XVID  
**Description:** It's compared against the torrent category.

**except-categories**
> **Description:** The exact opposite of **except-categories**. If a release matches this option, then it's NOT downloaded.

**match-sites**
> **Type:** Comma separated list  
**Example:** match-sites = tracker1, tracker2, tracker3  
**Description:** It's compared against the tracker. Use the full tracker name, eg. MyTracker or use one of the tracker types found in ~/.irssi/scripts/AutodlIrssi/trackers/*.tracker. Open one of the files and locate the **type="XYZ"** line. Use the value inside the quotes, eg. **XYZ**.

**except-sites**
> **Description:** The exact opposite of **match-sites**. If a release matches this option, then it's NOT downloaded.

**min-size**
> **Type:** Size  
**Example:** min-size = 200MB  
**Default:** 0  
**Description:** Used to filter out too small torrents.

**max-size**
> **Type:** Size  
**Example:** max-size = 2.5GB  
**Default:** any size is allowed  
**Description:** Used to filter out too big torrents. I recommend everyone to always use this option so you don't accidentally download a 100GB torrent! :D Set it to a reasonable value, eg. for TV-shows, set it to about twice the size of a normal episode (just in case it's a double-episode). This will automatically filter out season packs!

**shows**
> **Type:** Comma separated list  
**Example:** shows = The Simpsons, American Dad  
**Description:** This is for TV-shows, movies and artists/groups (what.cd/waffles only). autodl-irssi will automatically extract the TV-show/movie name from a scene release name. Example, The.Simpsons.S35E24.720p.HDTV-BLAH will match a **shows** option set to **the simpsons**. You don't need wildcards at all, though it's possible to use wildcards. It's recommended to use **shows** instead of **match-releases** if all you want is for the filter to match TV-shows or movies. what.cd and waffles: this will match against the artist/group.

**seasons**
> **Type:** List of numbers  
**Example:** seasons = 1, 3, 5-10  
**Description:** This is for TV-shows only. Unless the release matches one of the seasons, it's not downloaded.

**episodes**
> **Type:** List of numbers  
**Example:** episodes = 1, 3, 5-10  
**Description:** This is for TV-shows only. Unless the release matches one of the episodes, it's not downloaded.

**resolutions**
> **Type:** Comma separated list  
**Example:** resolutions = SD, 720p, 1080p  
**Description:** This is for TV-shows and movies only. Unless the release matches one of the resolutions, it's not downloaded. Valid resolutions are one or more of the following: **SD**, **480i**, **480p**, **576p**, **720p**, **810p**, **1080i**, **1080p**.

**sources**
> **Type:** Comma separated list  
**Example:** sources = HDTV, DVDRip, BluRay  
**Description:** This is for TV-shows and movies only. Unless the release matches one of the sources, it's not downloaded. Valid sources are one or more of the following: **DSR**, **PDTV**, **HDTV**, **HR.PDTV**, **HR.HDTV**, **DVDRip**, **DVDScr**, **BDr**, **BD5**, **BD9**, **BDRip**, **BRRip**, **DVDR**, **MDVDR**, **HDDVD**, **HDDVDRip**, **BluRay**, **WEB-DL**, **TVRip**, **CAM**, **R5**, **TELESYNC**, **TS**, **TELECINE**, **TC**. **TELESYNC** and **TS** are synonyms (you don't need both). Same for **TELECINE** and **TC**.

**encoders**
> **Type:** Comma separated list  
**Example:** encoders = x264, xvid  
**Description:** If you don't want windows WMV files, this option could be useful. :) Valid encoders are: **XviD**, **DivX**, **x264**, **h.264** (or **h264**), **mpeg2** (or **mpeg-2**), **VC-1** (or **VC1**), **WMV**, **Remux** (or **h.264 Remux**, **h264 Remux**, **VC-1 Remux**, **VC1 Remux**).

**years**
> **Type:** List of numbers  
**Example:** years = 1999, 2005-2010  
**Description:** Not all releases have a year in the torrent name, but if it does, you can use it to filter out too old or too new releases.

**albums**
> **Type:** Comma separated list  
**Example:** albums = Some album, Some other album, yet another one  
**Description:** what.cd/waffles only.

**formats**
> **Type:** Comma separated list  
**Example:** formats = MP3, FLAC  
**Description:** what.cd/waffles only. List the formats you want. Valid formats are: **MP3**, **FLAC**, **Ogg**, **AAC**, **AC3**, **DTS**.

**bitrates**
> **Type:** Comma separated list  
**Example:** bitrates = 192, V0 (vbr), lossless  
**Description:** what.cd/waffles only. List the bitrates you want. Some example values: **192**, **320**, **APS (VBR)**, **V2 (VBR)**, **V1 (VBR)**, **APX (VBR)**, **V0 (VBR)**, **q8.x (VBR)**, **Lossless**, **24bit Lossless**, **Other**.

**media**
> **Type:** Comma separated list  
**Example:** media = CD, WEB  
**Description:** what.cd/waffles only. List the media you want. Valid media are: **CD**, **DVD**, **Vinyl**, **Soundboard**, **SACD**, **DAT**, **Cassette**, **WEB**, **Other**.

**tags**
> **Type:** Comma separated list  
**Example:** tags = hip hop, rock  
**Description:** what.cd/waffles only. Unless at least one of your tags matches the release's tags, it's not downloaded. See also **except-tags** and **tags-any**.

**except-tags**
> **Type:** Comma separated list  
**Example:** except-tags = hip hop, rock  
**Description:** what.cd/waffles only. Same as **tags** except if it matches any/all of these, it's not downloaded. See also **tags** and **except-tags-any**.

**tags-any**
> **Type:** Boolean  
**Default:** true  
**Example:** tags-any = false  
**Description:** what.cd/waffles only. Decides how to match the **tags** option, ie., if any or all of the tags must match.

**except-tags-any**
> **Type:** Boolean  
**Default:** true  
**Example:** except-tags-any = true  
**Description:** what.cd/waffles only. Decides how to match the **except-tags** option, ie., if any or all of the tags must match.

**scene**
> **Type:** Boolean  
**Example:** scene = true  
**Description:** what.cd/waffles, and a few others. Some sites mark a release as scene or non-scene. Set it to true if you want only scene releases, false if you only want non-scene releases, or don't use this option if you don't care.

**log**
> **Type:** Boolean  
**Example:** log = true  
**Description:** what.cd/waffles. Set it to true if you only want releases with a log file, false if you don't want releases with log files, or don't use this option if you don't care.

**log-scores**
> **Type:** Number list  
**Default:** Any score allowed  
**Example:** log-scores = 90-95,96,98,100  
**Description:** what.cd/waffles. Set the log scores of the releases you want to match.

**cue**
> **Type:** Boolean  
**Example:** cue = true  
**Description:** what.cd. Set it to true if you only want releases with a cue file, false if you don't want releases with cue files, or don't use this option if you don't care.

**freeleech**
> **Type:** Boolean  
**Example:** freeleech = true  
**Description:** Only supported on a few [[trackers]]. Set to true if you only want to download freeleech releases. Set to false if you only want non-scene releases. Don't set if you don't care.

**freeleech-percents**
> **Type:** Number list  
**Example:** freeleech-percents = 50,75  
**Description:** Some trackers have multiple levels of freeleech. Set a list of numbers representing the percentages (without the % sign) of the releases you want to download.

**match-uploaders**
> **Type:** Comma separated list  
**Example:** match-uploaders = uploader1, uploader2  
**Description:** Use it to only download from certain uploaders.

**except-uploaders**
> **Description:** The exact opposite of **match-uploaders**. If a release matches this option, then it's NOT downloaded.

**max-pretime**
> **Type:** time-since string  
**Example:** max-pretime = 2 mins 3 secs  
**Description:** Some sites announce the pretime of the release. Use this to filter out old releases.

**max-downloads**
> **Type:** Integer  
**Example:** max-downloads = 15  
**Description:** Download no more than this number of torrents per week/month (see **max-downloads-per**). Remove the filter option or set it to a negative number to disable it.

**max-downloads-per**
> **Type:** String  
**Example:** max-downloads-per = week  
**Description:** Valid values are **day**, **week**, and **month**. See **max-downloads**.