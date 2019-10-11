# mcserver-stats-dbm
### Opis
Aby wszystko działało poprawnie ustaw ip serwera komendą `[p]ip <adres>` i wpisz komendę `[p]mcsetup` i poczekaj chwile na dane serwera.
Dane odświeżają się domyslnie co ok. 10 sekund

### RawData
**[p]IP**
```
{
  "name": "ip",
  "permissions": "ADMINISTRATOR",
  "restriction": "1",
  "_id": "WarFy",
  "actions": [
    {
      "comment": "<b>Created by krytyYT</b>",
      "color": "#ff8080",
      "name": "Comment"
    },
    {
      "comment": "Wiem ze to brzydkie ale jak chcesz to se edytuj ",
      "color": "#ffff80",
      "name": "Comment"
    },
    {
      "info": "0",
      "infoIndex": "1",
      "storage": "2",
      "varName": "ip",
      "name": "Store Command Params"
    },
    {
      "channel": "0",
      "varName": "",
      "message": ":ok_hand:",
      "storage": "0",
      "varName2": "",
      "iffalse": "0",
      "iffalseVal": "",
      "name": "Send Message"
    }
  ]
}
```
**[p]mcsetup**
```
{
  "name": "mcsetup",
  "permissions": "ADMINISTRATOR",
  "restriction": "1",
  "_id": "rtbCb",
  "actions": [
    {
      "comment": "<b>Created by krytyYT</b>",
      "color": "#ff8080",
      "name": "Comment"
    },
    {
      "channelName": "IP: ${serverVars(\"ip\")}",
      "categoryID": "",
      "bitrate": "",
      "userLimit": "",
      "storage": "2",
      "varName": "motd",
      "name": "Create Voice Channel"
    },
    {
      "channelName": "Wersja:",
      "categoryID": "",
      "bitrate": "",
      "userLimit": "",
      "storage": "2",
      "varName": "version",
      "name": "Create Voice Channel"
    },
    {
      "channelName": "Sloty:",
      "categoryID": "",
      "bitrate": "",
      "userLimit": "",
      "storage": "2",
      "varName": "players",
      "name": "Create Voice Channel"
    },
    {
      "storage": "4",
      "varName": "motd",
      "permission": "CONNECT",
      "state": "1",
      "name": "Set Voice Channel Perms"
    },
    {
      "storage": "4",
      "varName": "version",
      "permission": "CONNECT",
      "state": "1",
      "name": "Set Voice Channel Perms"
    },
    {
      "storage": "4",
      "varName": "players",
      "permission": "CONNECT",
      "state": "1",
      "name": "Set Voice Channel Perms"
    },
    {
      "call": "10",
      "name": "Jump to Action"
    },
    {
      "name": "End Action Sequence"
    },
    {
      "token": "",
      "user": "",
      "pass": "",
      "url": "https://api.mcsrvstat.us/ping/${serverVars(\"ip\")}",
      "path": "$.players.online",
      "storage": "1",
      "varName": "online",
      "debugMode": "1",
      "headers": "",
      "name": "Store Json From WebAPI"
    },
    {
      "token": "",
      "user": "",
      "pass": "",
      "url": "https://api.mcsrvstat.us/ping/${serverVars(\"ip\")}",
      "path": "$.players.max",
      "storage": "1",
      "varName": "max",
      "debugMode": "1",
      "headers": "",
      "name": "Store Json From WebAPI"
    },
    {
      "token": "",
      "user": "",
      "pass": "",
      "url": "https://api.mcsrvstat.us/ping/${serverVars(\"ip\")}",
      "path": "$.version.name",
      "storage": "1",
      "varName": "ver",
      "debugMode": "1",
      "headers": "",
      "name": "Store Json From WebAPI"
    },
    {
      "storage": "4",
      "varName": "version",
      "toChange": "name",
      "newState": "Wersja: ${tempVars(\"ver\")}",
      "name": "Edit Channel"
    },
    {
      "storage": "4",
      "varName": "players",
      "toChange": "name",
      "newState": "Sloty: ${tempVars(\"online\")}/${tempVars(\"max\")}",
      "name": "Edit Channel"
    },
    {
      "time": "10",
      "measurement": "1",
      "name": "Wait"
    },
    {
      "call": "10",
      "name": "Jump to Action"
    },
    {
      "comment": "<b>Created by krytyYT</b>",
      "color": "#ff8080",
      "name": "Comment"
    }
  ]
}
```
