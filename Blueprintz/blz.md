# BLZ (File Format)


## Introduction
**BLZ** is the (custom) file format/extention the editor uses to save projects in. It is custom designed and made for ease of use and so its lightweight/small.
Our file is just json but compressed with a custom compression algorithm, when the file is decompressed the JSON has this model. (*see the codesample below*)

## Datastructure
The decompressed JSON has this model. (*see the codeblock below*)

```json
{
  "projectName": "",
  "projectDescription": "Blueprintz Generator",
  "map": "town",
  "fireworks": [
    {
      "id": "guid",
      "fireworkIndentifier": "PreloadedTube_MrBeats",
      "position": {
        "X": 0,
        "Y": 0,
        "Z": 0
      },
      "rotation": {
        "X": 0,
        "Y": 0,
        "Z": 0,
        "W": 0,
        "IsIdentity": false
      },
      "isKinematic": true
    }
  ],
  "fuses": [
    {
      "id": "guid",
      "idConnectionA": "guidFireworkA",
      "idConnectionB": "guidFireworkB",
      "speed": 1
    }
  ]
}
```

```note
The design of the model is still in progress, and will change in the future!
```

Page Contributors: @daanbreur
