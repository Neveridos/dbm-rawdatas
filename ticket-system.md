# Ticket System 
### Opis
Ticket System z pewnymi ficzurami.
### Instalacja
Ustawiamy rolę komendą `[p]setrole` i tyle z konfiguracji XD
### RawDaty
[p]setrole
```
{
  "name": "setrole",
  "permissions": "ADMINISTRATOR",
  "restriction": "1",
  "_id": "EfpqN",
  "actions": [
    {
      "comment": "<b>Created by krytyYT</b>",
      "color": "#ff8080",
      "name": "Comment"
    },
    {
      "comment": "Wiem że brzydkie ale jak chcesz to se zmień okej?",
      "color": "#ffff80",
      "name": "Comment"
    },
    {
      "info": "3",
      "infoIndex": "1",
      "storage": "2",
      "varName": "role",
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
[p]ticket
```
{
  "name": "ticket",
  "permissions": "NONE",
  "restriction": "1",
  "_id": "zArLS",
  "actions": [
    {
      "comment": "<b>Created by krytyYT</b>",
      "color": "#ff8080",
      "name": "Comment"
    },
    {
      "info": "19",
      "storage": "3",
      "varName2": "prefix",
      "name": "Store Bot Client Info"
    },
    {
      "storage": "1",
      "varName": "nr",
      "min": "100000",
      "max": "999999999",
      "name": "Generate Random Number"
    },
    {
      "channelName": "support-${tempVars(\"nr\")}",
      "categoryID": "",
      "topic": "Ticket nr: ${tempVars(\"nr\")}",
      "position": "",
      "storage": "1",
      "varName": "chan",
      "name": "Create Text Channel"
    },
    {
      "channel": "3",
      "varName": "chan",
      "member": "1",
      "varName2": "",
      "permission": "READ_MESSAGES",
      "state": "0",
      "name": "Set Member Channel Perms"
    },
    {
      "channel": "3",
      "varName": "chan",
      "member": "1",
      "varName2": "",
      "permission": "SEND_MESSAGES",
      "state": "0",
      "name": "Set Member Channel Perms"
    },
    {
      "channel": "3",
      "varName": "chan",
      "role": "4",
      "varName2": "role",
      "permission": "READ_MESSAGES",
      "state": "0",
      "name": "Set Role Channel Perms"
    },
    {
      "comment": "<b>Created by krytyYT</b>",
      "color": "#ff8080",
      "name": "Comment"
    },
    {
      "channel": "3",
      "varName": "chan",
      "role": "4",
      "varName2": "role",
      "permission": "SEND_MESSAGES",
      "state": "0",
      "name": "Set Role Channel Perms"
    },
    {
      "storage": "3",
      "varName": "chan",
      "permission": "SEND_MESSAGES",
      "state": "1",
      "name": "Set Channel Permissions"
    },
    {
      "storage": "3",
      "varName": "chan",
      "permission": "READ_MESSAGES",
      "state": "1",
      "name": "Set Channel Permissions"
    },
    {
      "title": "Ticket Został utworzony!",
      "author": "",
      "color": "RANDOM",
      "url": "",
      "authorIcon": "",
      "authorUrl": "",
      "imageUrl": "",
      "thumbUrl": "",
      "timestamp": "false",
      "text": "",
      "year": "",
      "month": "",
      "day": "",
      "hour": "",
      "minute": "",
      "second": "",
      "storage": "1",
      "varName": "em",
      "name": "Create Embed Message"
    },
    {
      "storage": "1",
      "varName": "em",
      "message": "Twój ticket to: ${tempVars(\"chan\")}",
      "name": "Set Embed Description"
    },
    {
      "storage": "1",
      "varName": "em",
      "channel": "0",
      "varName2": "",
      "storage3": "0",
      "varName3": "",
      "name": "Send Embed Message"
    },
    {
      "title": "Ticket nr: ${tempVars(\"nr\")}",
      "author": "",
      "color": "RANDOM",
      "url": "https://github.com/krytyYT/dbm-rawdatas",
      "authorIcon": "",
      "authorUrl": "",
      "imageUrl": "",
      "thumbUrl": "",
      "timestamp": "false",
      "text": "",
      "year": "",
      "month": "",
      "day": "",
      "hour": "",
      "minute": "",
      "second": "",
      "storage": "1",
      "varName": "emb",
      "name": "Create Embed Message"
    },
    {
      "storage": "1",
      "varName": "emb",
      "message": "`${globalVars(\"prefix\")}zamknij` - Zamyka ticket\n`${globalVars(\"prefix\")}usun` - Usuwa ticket",
      "name": "Set Embed Description"
    },
    {
      "storage": "1",
      "varName": "emb",
      "channel": "5",
      "varName2": "chan",
      "storage3": "0",
      "varName3": "",
      "name": "Send Embed Message"
    },
    {
      "comment": "<b>Created by krytyYT</b>",
      "color": "#ff8080",
      "name": "Comment"
    }
  ]
}
```
[p]zamknij
```
{
  "name": "zamknij",
  "permissions": "NONE",
  "restriction": "1",
  "_id": "yNUYn",
  "actions": [
    {
      "channel": "0",
      "varName": "",
      "info": "2",
      "storage": "1",
      "varName2": "name",
      "name": "Store Channel Info"
    },
    {
      "storage": "1",
      "varName": "name",
      "comparison": "10",
      "value": "support",
      "iftrue": "0",
      "iftrueVal": "",
      "iffalse": "2",
      "iffalseVal": "7",
      "name": "Check Variable"
    },
    {
      "channel": "0",
      "varName": "",
      "member": "1",
      "varName2": "",
      "permission": "SEND_MESSAGES",
      "state": "2",
      "name": "Set Member Channel Perms"
    },
    {
      "channel": "0",
      "varName": "",
      "message": "Pomyślnie zamknięto ticket!",
      "storage": "0",
      "varName2": "",
      "iffalse": "0",
      "iffalseVal": "",
      "name": "Send Message"
    },
    {
      "channel": "0",
      "varName": "",
      "message": "Aby usunąć kanał wpisz `${globalVars(\"prefix\")}usun`!",
      "storage": "0",
      "varName2": "",
      "iffalse": "0",
      "iffalseVal": "",
      "name": "Send Message"
    },
    {
      "name": "End Action Sequence"
    },
    {
      "channel": "0",
      "varName": "",
      "message": "Ten kanał nie może zostać zamknięty tą komendą!",
      "storage": "0",
      "varName2": "",
      "iffalse": "0",
      "iffalseVal": "",
      "name": "Send Message"
    },
    {
      "comment": "<b>Created by krytyYT</b>",
      "color": "#ff8080",
      "name": "Comment"
    }
  ]
}
```
[p]usun
```
{
  "name": "usun",
  "permissions": "NONE",
  "restriction": "1",
  "_id": "asQcV",
  "actions": [
    {
      "channel": "0",
      "varName": "",
      "info": "2",
      "storage": "1",
      "varName2": "name",
      "name": "Store Channel Info"
    },
    {
      "storage": "1",
      "varName": "name",
      "comparison": "10",
      "value": "support",
      "iftrue": "0",
      "iftrueVal": "",
      "iffalse": "2",
      "iffalseVal": "6",
      "name": "Check Variable"
    },
    {
      "storage": "0",
      "varName": "",
      "name": "Delete Channel"
    },
    {
      "channel": "0",
      "varName": "",
      "message": "Pomyślnie usunięto ticket!",
      "storage": "0",
      "varName2": "",
      "iffalse": "0",
      "iffalseVal": "",
      "name": "Send Message"
    },
    {
      "name": "End Action Sequence"
    },
    {
      "channel": "0",
      "varName": "",
      "message": "Ten kanał nie może zostać usunięty tą komendą!",
      "storage": "0",
      "varName2": "",
      "iffalse": "0",
      "iffalseVal": "",
      "name": "Send Message"
    },
    {
      "comment": "<b>Created by krytyYT</b>",
      "color": "#ff8080",
      "name": "Comment"
    }
  ]
}
```
