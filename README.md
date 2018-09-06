# TautulliScripts
Tautulli Plex Scripts

Upgrade of the original script from https://github.com/blacktwin/JBOPS

***
06/o9/2018 - streamSubscription

Added function streamSubscription

Exemple of userConfig.ini :
```
[18422708]
friendly_name = John Doe
user_id = 18422708
subscription_end = 06/09/2018
```
never as value = account unlimited.

date in the following format 06/09/2018 (DAY/MONTH/YEAR) will kill the stream if date is greater than current day.

```
--jbop streamSubscription --sessionId {session_id} --userId {user_id}
```


***
Added functions: streamAllowed and configUser

Usage:

From the terminal:

Create the configuration file with the command:
python3 kill_stream.py --jbop configUser

A file "userConfig.ini" will be created in the script folder.

Exemple of userConfig.ini :
```
[18422708]
friendly_name = John Doe
user_id = 18422708
user_slot = 1 ; Maximum number of streams allowed for the selected user. Default value is 1
```
In Tautulli:

Notification Agents -> Script -> [Triggers -> Playback Start]
[Arguments -> Playback Start]:
```
--jbop streamAllowed --username {username} --sessionId {session_id} --streamCount {user_streams} --userId {user_id}
```
***
Config file is automatically synced with Tautulli database.
Users are added and removed according to Tautulli users list.
