# Setting up macOS *Time Machine* Backups on FAU Servers

[![Actions Status](https://wdp9fww0r9.execute-api.us-west-2.amazonaws.com/production/badge/soztag/backup)](https://github.com/soztag/backup/actions)

**This documentation lives on GitHub.
To raise issues or make changes, go to [`https://github.com/soztag/backup`](https://github.com/soztag/backup)**.

![xkcd 1360: *Old Files*](https://imgs.xkcd.com/comics/old_files.png)


## Why You Should Care

Because ... backups.
*Everyone* should have backups.


## Limitations

This only works when you're physically connected to the FAU.
*Do not try to run backups via a VPN connection!*
You should also use an ethernet connection if at all possible to avoid overloading the local WiFi.


## Setup

1. Connect to the FAU network drive on which to backup your data.
  You only have to do this *once*, and this only works from inside the FAU network.  
  ![Go](https://github.com/soztag/backup/blob/master/go.png?raw=true){ width=50% }
2. Enter the address for the network drive: `afp://timemachine.rrze.uni-erlangen.de/TimeMachine`.  
  ![Connect](https://github.com/soztag/backup/blob/master/connect.png?raw=true){ width=50% }
3. Navigate to `Systems Preferences > Time Machine`.  
  ![Preferences](https://github.com/soztag/backup/blob/master/prefs.png?raw=true){ width=50% }
4. Add a new Time Machine destination.  
  ![Add](https://github.com/soztag/backup/blob/master/add.png?raw=true){ width=50% }
5. Select the server drive `"TimeMachine"` as the backup destination.
  **Always remember to check "encrypt backup"**.  
  ![Select](https://github.com/soztag/backup/blob/master/select.png?raw=true){ width=50% }
6. Enter your [IdM-credentials](https://www.rrze.fau.de/infocenter/kontakt-hilfe/idm/) if prompted (usernames are cryptic alphanumerics).  
  ![IDM](https://github.com/soztag/backup/blob/master/idm.png?raw=true){ width=50% }
7. You're done.
  Completing the first backup is going to take some time (might be days).
  Later, incremental backups will be much faster.
  Remember to connect your computer via ethernet for the first backup.
  Once you're done, a complete backup should look like this:  
  ![Ready](https://github.com/soztag/backup/blob/master/ready.png?raw=true){ width=50% }


## Restoring Data

To restore lost or changed files, click "Enter Time Machine" in Finder (and some other programs, which may natively support Time Machine).

![Enter](https://github.com/soztag/backup/blob/master/enter.png?raw=true){ width=50% }

Learn more about Time Machine on [Apple Support websites](https://support.apple.com/en-us/HT201250).

To restore a new or empty harddrive from a Time Machine backup, contact the [FAUMac team](https://www.rrze.fau.de/hard-software/betriebssysteme/apple-macos-und-ios/).


## Administration

To be able to run Time Machine backups on FAU servers, your team or organization needs to buy "[Basic Linux Storage NFS](https://www.rrze.fau.de/hard-software/betriebssysteme/linux/#collapse_3)" from RRZE.
This currently costs €10/500GB.

To change the storage quota, email an updated form to `rrze-mac@fau.de`.
In addition to the total quota, FAUMac must also know the usernames (IdM) and quote *per* user.

SOZTAG's current quota is 1TB, 200GB/person.
The order forms can be found on `FAUbox/SOZTAG/IT/RRZE Dienstleistungen/Storage`.
