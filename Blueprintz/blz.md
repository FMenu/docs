# BLZ (File Format)


## Introduction
**BLZ** is the (custom) file format/extention the editor uses to save projects in. It is custom designed and made for ease of use and so its lightweight/small.
Our file is just json but compressed with a custom compression algorithm, when the file is decompressed the JSON has this model. (*see the codesample below*)

## Datastructure
The decompressed JSON has this model. (*see the codeblock below*)

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

## Algorithm

To compress the JSON you would do the following steps.

1. Convet the encoded JSON to BSON data.
2. Use a Ziping algorithm to further compress the string.
3. Convert the byte Array from the Zipping algorithm to a Base64String and write it to a .blz file.

## Code Samples
In this section are a few codesamples on how to intergrate the algorithm's. These are in pseudo-code.

The code-block below contains the pseudo-code for compression written in C#.

The BSON generation:
```r
var obj = JsonConvert.DeserializeObject(json);
JsonSerializer serializer = new JsonSerializer();
MemoryStream stream = new MemoryStream();
BsonWriter writer = new BsonWriter(stream);
serializer.Serialize(writer, obj);
string output = System.Text.Encoding.ASCII.GetString(stream.ToArray());
```
Zipping algorithm:
```r
public static byte[] Zip(string str)
{
  var bytes = System.Text.Encoding.UTF8.GetBytes(str);
  using (var msi = new MemoryStream(bytes))
  using (var mso = new MemoryStream()
  {
    using (var gs = new GZipStream(mso, CompressionMode.Compress))
    {
      CopyTo(msi, gs);
    }
    return mso.ToArray();
  }
}
```

The following code-block contains the pseudo-code for decompression.

```r
Nothing here yet.
```

Page Contributors: @daanbreur, @jjblock21
