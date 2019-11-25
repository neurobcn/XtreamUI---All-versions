# XtreamUI-R19AE
Xtream UI 19AE

Entry for download

https://xtream-ui.com/donator.php

Username: wissdz27
Password: wissel24101201

forum_password
221901
forum_username
rjubranjr

or use
https://xtream-ui.com/install/donator.php?username=XXXXXX&password=XXXXX


Backup database whmcs of

https://clients.first-store.fr/admin/index.php (admin - wissel24101201)

ftp://root:PilaritO@paca.dyndns.org/

19

Changelog:
Redone M3U import for streams, should be better now! Should work for those who it didn't work for before.
Added M3U Import / Folder Import for Movies. Scans TMDb in the background using a cronjob.
Added re-process TMDb to Mass Edit.
Fixed mass delete of episodes.
Added notes to Streams, Movies and Episodes page.

R19A - 21/11/2019 16:15

Added folder watching for movies, cron and assorted pages (dropdown for settings).
Fixed transcoding profile creator.
Fixed target container on mass import.


18

[b][u]THIS ISN'T A REQUEST THREAD - PLEASE STOP POSTING REQUESTS HERE! Use the dedicated forum[/u][/b]
[b][u]ANYONE SHARING THIS TO NON-DONATORS WILL BE BANNED[/u][/b]



Last thread got a little too long... Fixed a few things, lets' try again.

[b]Don't Mention These Bugs:[/b]
[list]M3U Import Not Working - I've tested it multiple times with multiple M3U's, works fine for me.[/list]
[list]CPU 100% or high memory usage - Nothing to do with Xtream UI, ffmpeg or php or something is using all your resources for some reason.[/list]
[list]Many connections from an account with 1 connection - Again not handled by Xtream UI, this is an XC bug and I don't know what causes it.[/list]
[list]Transcoding taking a long time - Another thing absolutely not handled by Xtream UI.[/list]




[b]Changelog:[/b]
[list]Ability to send MAG events from the MAGs page.[/list]
[list]New transcode profile generator with all options available.[/list]
[list]Added per-user Package Override options, edit the reseller to see these options.[/list]
[list]Streams page changed slightly, a bit clearer (added timeshift icon, icons for status and moved current source).[/list]
[list]Added option in Settings to change from normal API to localhost API. Tick this box if you're having issues with API.[/list]
[list]Fixed M3U import issues with 17B.[/list]
[list]Fixed MAG search for lowercase MAC addresses.[/list]
[list]Username is now non-changeable for resellers who can't change passwords.[/list]
[list]Unblocking IP's now unblocks from load balancers too.[/list]
[list]Added restart on edit / start on creation to Movies and Streams.[/list]
[list]Revamped dashboard, all servers visible in overview.[/list]
[list]Added stream tools to allow you to tranfers DNS or move streams from server to server.[/list]
[list]If Download Images is ticked in settings, stream icons are now downloaded too. Fixed edit redownloading images.[/list]
[list]Added RTMP IP's for RTMP push. In settings dropdown.[/list]
[list]Ability to delete 2 factor auth credentials for a user incase they forget their code.[/list]
[list]More settings added, persistent connections.[/list]
[list]Returns to location after login timeout due to inactivity.[/list]
[list]Combined stream categories to cover Streams, Movies & Series.[/list]
[list]Numerous bugfixes.[/list]
[list]Added Manual Channel Ordering - in settings dropdown.[/list]
[list]Changed Bouquet order again, now simpler and maybe quicker.[/list]
[list]Fix setting for localhost API.[/list]
[list]Added download button to Backups page in Settings.[/list]
[list]Removed requirement for owner on users for admins only. Fixes legacy problems.[/list]
[list]Add another setting to allow changing usernames for resellers.[/list]
[list]Changed stream check to check for URL instead of name on M3U import.[/list]
[list]Added series & episodes.[/list]
[list]Added season ordering.[/list]
[list]Added mass delete series & episodes.[/list]
[list]Added mass edit series & episodes.[/list]
[list]Fixed stream tools DNS replacement.[/list]
[list]Fixed reseller override issues.[/list]
[list]Replaced TMDb module with better version.[/list]
[list]Fixed player for VOD.[/list]
[list]Fixed mass delete not deleting actual files.[/list]
[list]Fixed only one IP / User Agent saving in restrictions.[/list]
[list]Added multiple episode import.[/list]
[list]Added a bunch of new settings.[/list]
[list]Fixed last modified date for series.[/list]
[list]Added tooltips for every button.[/list]
[list]Fixed episode number when adding episodes.[/list]
[list]Fixed trial credits in packages.[/list]

[list]Implemented Smarters Reseller API, courtesy of Smarters themselves.
  - More information to come on this from Smarters, however check out the PHP file for api calls.
  - To enable this for a Group, edit the Group and check the API switch.
  - The reseller can generate their API key from their dashboard.
  - http://test.com:25500/api/reseller_api.php?api_key=KEY&action=ACTION[/list]

[b]Still To Come (hopefully in this order):[/b]
[list]Admin Permissions[/list]
[list]Mass Edit Registered Users[/list]
[list]M3U Import / Folder Import for Movies & Series[/list]
[list]Folder Watching[/list]
[list]Created Channels[/list]
[list]Sonarr / Radarr / Plex Integration[/list]


[b]BACKUPS[/b]
If backups aren't working for you, run the following command:
[code]sudo chown xtreamcodes:xtreamcodes /home/xtreamcodes/iptv_xtream_codes/adtools/backups/[/code]


[b]PROCESS MONITORING[/b]
So I've made a process killer that checks all PID's in the database against live PID's on the server, killing any it doesn't need. This could potentially help people running into CPU issues, or just help in general as XC isn't the best at killing PID's.

pid_monitor.zip


To install it, download the file from above and extract it here (on each server you want it running on, include LB's):
[code]/home/xtreamcodes/iptv_xtream_codes/crons/[/code]


[b]INSTALL[/b]

For manual update, download the release from the link below.
[url]https://xtream-ui.com/donator.php[/url]


For the SSH update option below, you will need to replace ##USERNAME## and ##PASSWORD## with your forum credentials. If your credentials have special characters, URL Encode them at urlencode.org

[b]Update Script - Blocks GeoLite2.mmdb[/b]

[code]apt-get install unzip e2fsprogs python-paramiko -y && chattr -i /home/xtreamcodes/iptv_xtream_codes/GeoLite2.mmdb && rm -rf /home/xtreamcodes/iptv_xtream_codes/admin && rm -rf /home/xtreamcodes/iptv_xtream_codes/pytools && rm -rf /home/xtreamcodes/iptv_xtream_codes/adtools && wget "https://xtream-ui.com/install/donator.php?username=##USERNAME##&password=##PASSWORD##" -O /tmp/update.zip -o /dev/null && unzip /tmp/update.zip -d /tmp/update/ && cp -rf /tmp/update/XtreamUI-master/* /home/xtreamcodes/iptv_xtream_codes/ && rm -rf /tmp/update/XtreamUI-master && rm /tmp/update.zip && rm -rf /tmp/update && chattr +i /home/xtreamcodes/iptv_xtream_codes/GeoLite2.mmdb && /home/xtreamcodes/iptv_xtream_codes/start_services.sh[/code]






