---
sort: 1
---

# BLZ (File Format)

**BLZ** is the (custom) file format/extention the editor uses to save projects in. It is custom designed and made for ease of use and so its lightweight/small.
Our file is just json but compressed with a custom compression algorithm, when the file is decompressed the JSON has this model. (*see the codesample below*)

```json
{
  "map": "town",
  "zoom": 1,
  "fireworks": [
    {
      "id": "",
      "gameIndentifier": "",
      "x": 0,
      "y": 0
    }
  ],
  "fuses": [
    {
      "speed": 1,
      "connectedFireworks": [ "", "" ]
    }
  ]
}
```

```note
The design of the model is still in progress, and will change in the future!
```

To compress the JSON you would do the following steps.

1. xxx
2. xxx
3. xxx


Page Contributors: @daanbreur