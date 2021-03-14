# Blueprint JSON


## Introduction
The game saves the schematics/blueprints to a json file, check [#Datastructure](#Datastructure) for information about the datastructure. Check [#Types](#Types) for information about available types, eg FuseTypes, FireworksIds.

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