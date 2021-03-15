# Blueprint JSON


## Introduction
The game saves the schematics/blueprints to a json file, check [#Datastructure](#datastructure) for information about the datastructure. Check [#Types](#types) for information about available types, eg FuseTypes, FireworksIds. If you want codesamples go to [#Code Samples](#code_samples)

## Datastructure
The model of the json is the following (*see the codeblock below*)
```json
{
  "Author": "steamnameauthor",
  "Description": "an discription here",
  "ModifiedUtc": "utctimestring (2021-03-14T12:05:45.9043318Z)",
  "Entities": [
    {
      "EntityInstanceId": "uuid",
      "EntityDefinitionId": "firework_id",
      "CustomComponentData": {
        "RocketBehavior": {
          "CustomData": {
            "Position": {
              "X": 0,
              "Y": 0,
              "Z": 0
            },
            "Rotation": {
              "X": 0,
              "Y": 0,
              "Z": 0,
              "W": 0
            },
            "IsKinematic": false
          }
        }
      }
    },
    {
      "EntityInstanceId": "uuid",
      "EntityDefinitionId": "propanetank_id",
      "CustomComponentData": {
        "SaveableRigidbodyComponent": {
          "CustomData": {
            "isKinematic": false
          }
        },
        "SaveableTransformComponent": {
          "CustomData": {
            "position": {
              "X": 0,
              "Y": 0,
              "Z": 0
            },
            "rotation": {
              "X": 0,
              "Y": 0,
              "Z": 0,
              "W": 0
            },
            "localScale": {
              "X": 1.0,
              "Y": 1.0,
              "Z": 1.0
            }
          }
        }
      }
    },
    {
      "EntityInstanceId": "uuid",
      "EntityDefinitionId": "FuseConnectionEntityDefinition",
      "CustomComponentData": {
        "FuseConnection": {
          "CustomData": {
            "FuseTypeId": "FuseType",
            "FuseAOwnerId": "uuid_firework_1",
            "FuseBOwnerId": "uuid_firework_2"
          }
        }
      }
    }
  ]
}
```

## Types

```note
We are still working on the types section of this page.
```

### Rockets

- Rocket_AmazingGranny_Purple
- Rocket_AmazingGranny_Yellow
- Rocket_ChuteBoi_Blue
- Rocket_ChuteBoi_Green
- Rocket_ChuteBoi_Purple
- Rocket_ChuteBoi_Red
- Rocket_Cobber905Blue
- Rocket_Cobber905Green
- Rocket_Cobber905Red
- Rocket_Cobber905White
- Rocket_Cobber905Yellow
- Rocket_FearOfTheDark
- Rocket_Lunar2021_Oxblaster
- Rocket_Lunar2021_Oxcaper
- Rocket_Slammer
- Rocket_Strobilicious
- Rocket_StrobingBob
- Rocket_ThicBilly
- Rocket_Viper
- Rocket_ViperToo
- Rocket_WorldStopper

### Cakes

- Cake_2021
- Cake_BeeHive
- Cake_Boom
- Cake_ChineseWall
- Cake_Criminalis
- Cake_Dragon
- Cake_FatBill
- Cake_Lunar2021_Oxcelurator
- Cake_Lunar2021_OxWannaGo
- Cake_PopperBoi
- Cake_ShogunCrackling
- Cake_TheMessenger

### Firecrackers

- Firecracker_DoomBoom
- Firecracker_KokkenRulle
- Firecracker_LadyFingers
- Firecracker_MaleToes
- Firecracker_Snapper_Green
- Firecracker_Snapper_Purple
- Firecracker_Snapper_Red
- Firecracker_Snapper_White

### Novelties

- RomanCandle_InsaneScreamer
- RomanCandle_MicoolaCandle
- RomanCandle_MoStick
- RomanCandle_SantaWasHere
- RomanCandle_WandOfWizards
- Whistler_ScreamingPal
- Zipper_Mozzie

### Special

- Special_Shell_Tim
- Special_Rocket_KarlSon **NOT IN THE GAME YET**

### Tubes

- PreloadedTube_CodyBoom
- PreloadedTube_DraeBlast
- PreloadedTube_FoxUnlocked
- PreloadedTube_Imphentazia
- PreloadedTube_MrBeats
- PreloadedTube_Pawluten
- PreloadedTube_PewDiePew

### Props

- Prop_Prototype_Crate
- Prop_Town_PropaneTank_01
- Prop_Town_PropaneTank_02
- Prop_Town_PropaneTank_Tall_01
- Prop_Town_PropaneTank_Tall_02

### Fuses

Fuses are a bit different, in the EntityDefenitionId you use; FuseConnectionEntityDefinition. Then inside the FuseTypeId, Insde CustomComponentData/FuseConnection/CustomData you uses one of the following ids.

- SlowFuseConnectionType
- MediumFuseConnectionType
- FastFuseConnectionType
- InstantFuseConnectionType

## Code Samples

The UUID is a v4 uuid. Here are a few ways of generating them in different languages

```javascript
// NodeJS
const uuid = require('uuid');
console.log(uuid.v4());

// Browser
function uuid() {
  var uuid = "", i, random;
  for (i = 0; i < 32; i++) {
    random = Math.random() * 16 | 0;

    if (i == 8 || i == 12 || i == 16 || i == 20) {
      uuid += "-";
    }
    uuid += (i == 12 ? 4 : (i == 16 ? (random & 3 | 8) : random)).toString(16);
  }
  return uuid;
}
console.log(uuid())
```

```python
import uuid
print(str(uuid.uuid4()))
```

```csharp
System.Guid.NewGuid().ToString();
```