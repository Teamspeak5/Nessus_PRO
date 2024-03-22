# Nessus PRO Installation Guide with Latest Plugin Set [NO CRACK NEEDED] [UPDATED 2024]
## Instroduction
Let's bring back to good old Nessus Pro installation guide here! Some of you already know what I'm talking about but for others, let's go.
Source : [https://breachforums.cx](https://breachforums.cx/Thread-Nessus-PRO-Installation-Guide-with-Latest-Plugin-Set-NO-NEED-CRACK-UPDATED-2024)

First of all, you need to download the official release of Nessus from Tenable website. I didn't try installing 10.x.x versions with this installation technique but as far as I know, it's the same and working but, for the sake of this guide, I'm also gonna share latest version I tried it with.

We can no longer download the 8.x.x version from Tenable website, I couldn't find it but I'm uploading the official one, no crack or anything, it's just an official installer, downloaded on 22.03.2024 by myself.

Download 10.x.x from here ([Official Website](https://www.tenable.com/downloads/nessus?loginAttempted=true))

## First Steps (For Windows and Linux)
1. Proceed with the installation do this for Windows and Linux:
2. Go to https://127.0.0.1:8834
3. Select "Managed Scanner" > select "enable tenable.sk" > Set your creds at the next screen and done.
4. Download the latest Nessus Plugin set from here [03.22.2024] (it's an official plugin set by Tenable)
([Official Website](https://plugins.nessus.org/v2/nessus.php?f=all-2.0.tar.gz&u=56b33ade57c60a01058b1506999a2431&p=1ee9c89d5379a119a56498f2d5dff674))

## Second Steps For Windows
1. Install Nessus (with the above instructions) and Download Plugin set.
2. Stop Nessus Service - ( net stop "Tenable Nessus" )
3. Open CMD as "administrator".
4. Change Files Attribute ( attrib -s -r -h "C:\ProgramData\Tenable\Nessus\nessus\plugins\*.*" )
5. Change Files Attribute ( attrib -s -r -h "C:\ProgramData\Tenable\Nessus\nessus\plugin_feed_info.inc" )
6. Update Plugins ( "C:\Program Files\Tenable\Nessus\nessuscli.exe" update "C:\DIRECTORY OF THIS FILE\all-2.0.tar.gz" )
7. Create File plugin_feed_info.inc in C:\ProgramData\Tenable\Nessus\nessus\plugins\ and put this inside :
```
PLUGIN_SET = "202402121405"; // keep the same as the one you already have
PLUGIN_FEED = "ProfessionalFeed (Direct)";
PLUGIN_FEED_TRANSPORT = "Tenable Network Security Lightning";
```
8. Copy File To Folder ( copy "C:\ProgramData\Tenable\Nessus\nessus\plugins\plugin_feed_info.inc" "C:\ProgramData\Tenable\Nessus\nessus\" )
9. Change Files Attribute ( attrib +s +r +h "C:\ProgramData\Tenable\Nessus\nessus\plugins\*.*" )
10. Change Files Attribute ( attrib +s +r +h "C:\ProgramData\Tenable\Nessus\nessus\plugin_feed_info.inc" )
11. Change Files Attribute ( attrib -s -r -h "C:\ProgramData\Tenable\Nessus\nessus\plugins\plugin_feed_info.inc" )
12. Start Nessus Service - ( net start "Tenable Nessus" )


## Second Steps For Linux
1.  After installation (guide above) stop nessus service > "sudo systemctl stop nessusd.service"
2.  sudo /opt/nessus/sbin/nessuscli update all-2.0.tar.gz
3.  Create a file named "plugin_feed_info.inc" in "/opt/nessus/var/nessus/" and put this inside:
```
PLUGIN_SET = "202402121405"; // keep the same as the one you already have
PLUGIN_FEED = "ProfessionalFeed (Direct)";
PLUGIN_FEED_TRANSPORT = "Tenable Network Security Lightning";
```
4.   sudo cp /opt/nessus/var/nessus/plugin_feed_info.inc /opt/nessus/lib/nessus/plugins/plugin_feed_info.inc
5.   sudo cp /opt/nessus/var/nessus/plugin_feed_info.inc /opt/nessus/var/nessus/.plugin_feed_info.inc
6.   sudo chattr +i /opt/nessus/var/nessus/plugin_feed_info.inc /opt/nessus/var/nessus/.plugin_feed_info.inc
7.   sudo chattr +i -R /opt/nessus/lib/nessus/plugins
8.   sudo chattr -i /opt/nessus/lib/nessus/plugins/plugin_feed_info.inc
9.   sudo chattr -i /opt/nessus/lib/nessus/plugins
10.  start the service > "sudo systemctl start nessusd.service"

Enjoy! :)


Pleae support the original sources that made me make this unique reddit post:
https://github.com/harshdhamaniya/nessuscrack
[nessuscrack @github.com](https://github.com/harshdhamaniya/nessuscrack)
[tld @breachforums.cx](https://breachforums.cx/Thread-Nessus-PRO-Installation-Guide-with-Latest-Plugin-Set-NO-NEED-CRACK-UPDATED-2024)
