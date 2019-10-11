# nuke-dbm-rawdata
```
{
  "name": "nuke",
  "permissions": "NONE",
  "restriction": "1",
  "_id": "utcsz",
  "actions": [
    {
      "comment": "<b>Created by krytyYT</b>",
      "color": "#ff8080",
      "name": "Comment"
    },
    {
      "channel": "0",
      "varName": "",
      "info": "2",
      "storage": "1",
      "varName2": "name",
      "name": "Store Channel Info"
    },
    {
      "channel": "0",
      "varName": "",
      "info": "5",
      "storage": "1",
      "varName2": "pos",
      "name": "Store Channel Info"
    },
    {
      "channel": "0",
      "varName": "",
      "info": "3",
      "storage": "1",
      "varName2": "cat",
      "name": "Store Channel Info Things"
    },
    {
      "category": "1",
      "varName": "cat",
      "info": "0",
      "storage": "1",
      "varName2": "cate",
      "name": "Store Category Info"
    },
    {
      "storage": "0",
      "varName": "",
      "name": "Delete Channel"
    },
    {
      "channelName": "${tempVars(\"name\")}",
      "categoryID": "${tempVars(\"cate\")}",
      "topic": "RawData by krytyYT | https://top.gg/bot/623562796835143710",
      "position": "${tempVars(\"pos\")}",
      "storage": "1",
      "varName": "chan",
      "name": "Create Text Channel"
    },
    {
      "channel": "5",
      "varName": "chan",
      "message": "Wszystkie wiadomości zostały usunięte!\nhttps://imgur.com/LIyGeCR",
      "storage": "0",
      "varName2": "",
      "iffalse": "0",
      "iffalseVal": "",
      "name": "Send Message"
    }
  ]
}
