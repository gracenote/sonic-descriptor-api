# sonic-descriptor-api

## prerequisites
Request APIKEY for Sonic Descriptor API access. Please contact Gracenote GMD product team.

## Request

### Path
```
/tracks/isrc
```

### Parameters
| Parameter | Type | Default | Description |
|-|-|-|-|
| id | Required | N/A | ISRC code of the track to lookup |
| limit | Optional | 10 | Maximum number of objects to return in a query response, Valid range: 1 to 50 |
| offset | Optional | 0 | Number of objects to skip/offset into a list of objects, used for pagination, valid range: 1 and above |

### Headers
| name | Type | Available Value (Default) | Description |
|-|-|-|-|
| GN.GMD.package | Optional | Discovery \| advancedDiscovery (Discovery) | Discovery package only receives top sonic descriptor with ID, genericName and localized labels; while Advanced Discovery package receives the whole depth of descriptors |

## Response

### Response fields
| Field | Description |
|-|-|
| Meta | Showing the track objects total number, count and offset |
| Data | Showing the detailed track objects |

### Meta
| Field | Description |
|-|-|
| total | the total number of track objects |
| count | the track objects number in this data filed |
| offset | the offset of track objects from the first one |

### Data
| Field | Description |
|-|-|
| objectType | Type of returned object. |
| trackName | Name of the returned track. |
| album | Object that holds album related data |
| album::albumName | Name of the album associated with the track |
| album::releaseType | Release type (OAR type, or Original Album Release type) of the album associated with the track |
| artist | Object that holds artist related data |
| artist::artistName | Name of the track artist |
| sonicDescriptors | Object that holds sonic descriptor objects (mood / tempo / style) |
| sonicDescriptors::moods descriptors | An array of moods from highest weight to lowest (Advanced Discovery package), or top mood (Discovery package) |
| sonicDescriptors::styles descriptors | An array of styles from highest weight to lowest (Advanced Discovery package), or top style (Discovery package) |
| sonicDescriptors::tempo descriptors | An array of tempos from highest weight to lowest (Advanced Discovery package), or top tempo (Discovery package) |

## Example

### request
```
curl -H "GN.GMD.package: advancedDiscovery" -i "https://api.gmd.music.gracenote.com/v1.1/tracks/isrc?id=USUM72013355&apikey={apikey}}"
```

### response
```
{
  "meta": {
    "total": 17,
    "count": 17,
    "offset": 0
  },
  "data": [
    {
      "objectType": "Track",
      "trackName": "For The Night (Featuring Lil Baby, DaBaby)",
      "album": {
        "albumName": "Gaming Hits 2021",
        "releaseType": "Commercial - Multi Artist Collection"
      },
      "artist": {
        "artistName": "Various Artists"
      },
      "sonicDescriptors": {
        "moods": [
          {
            "ID": "90018",
            "genericName": "Edgy Slow Sensual Groove",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91144",
                  "label": "Sensual"
                },
                {
                  "level": 2,
                  "descriptorID": "91286",
                  "label": "Intimate"
                }
              ]
            },
            "weight": "31"
          },
          {
            "ID": "90019",
            "genericName": "Serious Upfront Expressive Sensual Beats",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91144",
                  "label": "Sensual"
                },
                {
                  "level": 2,
                  "descriptorID": "91286",
                  "label": "Intimate"
                }
              ]
            },
            "weight": "19"
          },
          {
            "ID": "34197",
            "genericName": "Dark Groovy / Savvy",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91308",
                  "label": "Dark Groovy"
                }
              ]
            },
            "weight": "18"
          },
          {
            "ID": "90028",
            "genericName": "Hurt, Caring, Pride, Perseverance \u0026 Hope",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91295",
                  "label": "Cool Confidence"
                }
              ]
            },
            "weight": "7"
          },
          {
            "ID": "34193",
            "genericName": "Cool Confident Wary",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91311",
                  "label": "Wary / Defiant"
                }
              ]
            },
            "weight": "7"
          },
          {
            "ID": "90041",
            "genericName": "Dark Strolling Edgy Cool Confessional",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91311",
                  "label": "Wary / Defiant"
                }
              ]
            },
            "weight": "6"
          },
          {
            "ID": "90020",
            "genericName": "Expressive Pulsing Desirous Groove",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91144",
                  "label": "Sensual"
                },
                {
                  "level": 2,
                  "descriptorID": "91286",
                  "label": "Intimate"
                }
              ]
            },
            "weight": "5"
          },
          {
            "ID": "90029",
            "genericName": "Kick-Back Dreamy Straightforward",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91295",
                  "label": "Cool Confidence"
                }
              ]
            },
            "weight": "2"
          },
          {
            "ID": "90209",
            "genericName": "Epic Dark Serious / Building Hope",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91158",
                  "label": "Empowering"
                },
                {
                  "level": 2,
                  "descriptorID": "91532",
                  "label": "Idealistic / Stirring"
                }
              ]
            },
            "weight": "2"
          },
          {
            "ID": "90038",
            "genericName": "Grim Unvarnished Truth",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91311",
                  "label": "Wary / Defiant"
                }
              ]
            },
            "weight": "2"
          }
        ],
        "styles": [
          {
            "ID": "84426",
            "genericName": "Mumble Rap",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89300",
                  "label": "Trap"
                }
              ]
            },
            "weight": "40"
          },
          {
            "ID": "88071",
            "genericName": "Trapsoul",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88905",
                  "label": "Soul/R\u0026B"
                },
                {
                  "level": 2,
                  "descriptorID": "89366",
                  "label": "Trapsoul"
                }
              ]
            },
            "weight": "25"
          },
          {
            "ID": "88072",
            "genericName": "Sad Trapsoul",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88905",
                  "label": "Soul/R\u0026B"
                },
                {
                  "level": 2,
                  "descriptorID": "89366",
                  "label": "Trapsoul"
                }
              ]
            },
            "weight": "16"
          },
          {
            "ID": "84278",
            "genericName": "Trap",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89300",
                  "label": "Trap"
                }
              ]
            },
            "weight": "6"
          },
          {
            "ID": "84424",
            "genericName": "Cloud Rap",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89300",
                  "label": "Trap"
                }
              ]
            },
            "weight": "6"
          },
          {
            "ID": "88067",
            "genericName": "Emo Rap",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89300",
                  "label": "Trap"
                }
              ]
            },
            "weight": "2"
          },
          {
            "ID": "84331",
            "genericName": "Urban Contemporary: R\u0026B",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88905",
                  "label": "Soul/R\u0026B"
                },
                {
                  "level": 2,
                  "descriptorID": "89364",
                  "label": "Contemporary R\u0026B"
                }
              ]
            },
            "weight": "1"
          },
          {
            "ID": "84282",
            "genericName": "Rap / R\u0026B Crossover",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89298",
                  "label": "Rap / R\u0026B Crossover"
                }
              ]
            },
            "weight": "1"
          }
        ],
        "tempos": [
          {
            "ID": "34094",
            "genericName": "60's",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "98",
              "hierarchyRegionName": "TEMPO-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "34283",
                  "label": "Medium Tempo"
                },
                {
                  "level": 2,
                  "descriptorID": "34290",
                  "label": "Medium"
                },
                {
                  "level": 3,
                  "descriptorID": "34311",
                  "label": "60s"
                }
              ]
            },
            "weight": "40"
          },
          {
            "ID": "34130",
            "genericName": "250's",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "98",
              "hierarchyRegionName": "TEMPO-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "43078",
                  "label": "Fast Tempo"
                },
                {
                  "level": 2,
                  "descriptorID": "34293",
                  "label": "Very Fast"
                },
                {
                  "level": 3,
                  "descriptorID": "34347",
                  "label": "250s"
                }
              ]
            },
            "weight": "34"
          },
          {
            "ID": "34108",
            "genericName": "120's",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "98",
              "hierarchyRegionName": "TEMPO-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "34283",
                  "label": "Medium Tempo"
                },
                {
                  "level": 2,
                  "descriptorID": "34291",
                  "label": "Medium Fast"
                },
                {
                  "level": 3,
                  "descriptorID": "34325",
                  "label": "120s"
                }
              ]
            },
            "weight": "25"
          }
        ]
      }
    },
    {
      "objectType": "Track",
      "trackName": "For The Night (Featuring Lil Baby, DaBaby)",
      "album": {
        "albumName": "Kućna Žurka",
        "releaseType": "Commercial - Multi Artist Collection"
      },
      "artist": {
        "artistName": "Various Artists"
      },
      "sonicDescriptors": {
        "moods": [
          {
            "ID": "90018",
            "genericName": "Edgy Slow Sensual Groove",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91144",
                  "label": "Sensual"
                },
                {
                  "level": 2,
                  "descriptorID": "91286",
                  "label": "Intimate"
                }
              ]
            },
            "weight": "36"
          },
          {
            "ID": "90019",
            "genericName": "Serious Upfront Expressive Sensual Beats",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91144",
                  "label": "Sensual"
                },
                {
                  "level": 2,
                  "descriptorID": "91286",
                  "label": "Intimate"
                }
              ]
            },
            "weight": "20"
          },
          {
            "ID": "34197",
            "genericName": "Dark Groovy / Savvy",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91308",
                  "label": "Dark Groovy"
                }
              ]
            },
            "weight": "17"
          },
          {
            "ID": "34193",
            "genericName": "Cool Confident Wary",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91311",
                  "label": "Wary / Defiant"
                }
              ]
            },
            "weight": "6"
          },
          {
            "ID": "90028",
            "genericName": "Hurt, Caring, Pride, Perseverance \u0026 Hope",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91295",
                  "label": "Cool Confidence"
                }
              ]
            },
            "weight": "5"
          },
          {
            "ID": "90041",
            "genericName": "Dark Strolling Edgy Cool Confessional",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91311",
                  "label": "Wary / Defiant"
                }
              ]
            },
            "weight": "5"
          },
          {
            "ID": "90020",
            "genericName": "Expressive Pulsing Desirous Groove",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91144",
                  "label": "Sensual"
                },
                {
                  "level": 2,
                  "descriptorID": "91286",
                  "label": "Intimate"
                }
              ]
            },
            "weight": "4"
          },
          {
            "ID": "90031",
            "genericName": "Sophisticated Cool Suave Empowered Groove",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91295",
                  "label": "Cool Confidence"
                }
              ]
            },
            "weight": "2"
          },
          {
            "ID": "90038",
            "genericName": "Grim Unvarnished Truth",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91311",
                  "label": "Wary / Defiant"
                }
              ]
            },
            "weight": "2"
          },
          {
            "ID": "90029",
            "genericName": "Kick-Back Dreamy Straightforward",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91295",
                  "label": "Cool Confidence"
                }
              ]
            },
            "weight": "2"
          }
        ],
        "styles": [
          {
            "ID": "84426",
            "genericName": "Mumble Rap",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89300",
                  "label": "Trap"
                }
              ]
            },
            "weight": "44"
          },
          {
            "ID": "88071",
            "genericName": "Trapsoul",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88905",
                  "label": "Soul/R\u0026B"
                },
                {
                  "level": 2,
                  "descriptorID": "89366",
                  "label": "Trapsoul"
                }
              ]
            },
            "weight": "22"
          },
          {
            "ID": "88072",
            "genericName": "Sad Trapsoul",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88905",
                  "label": "Soul/R\u0026B"
                },
                {
                  "level": 2,
                  "descriptorID": "89366",
                  "label": "Trapsoul"
                }
              ]
            },
            "weight": "14"
          },
          {
            "ID": "84278",
            "genericName": "Trap",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89300",
                  "label": "Trap"
                }
              ]
            },
            "weight": "7"
          },
          {
            "ID": "84424",
            "genericName": "Cloud Rap",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89300",
                  "label": "Trap"
                }
              ]
            },
            "weight": "6"
          },
          {
            "ID": "88067",
            "genericName": "Emo Rap",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89300",
                  "label": "Trap"
                }
              ]
            },
            "weight": "2"
          },
          {
            "ID": "84331",
            "genericName": "Urban Contemporary: R\u0026B",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88905",
                  "label": "Soul/R\u0026B"
                },
                {
                  "level": 2,
                  "descriptorID": "89364",
                  "label": "Contemporary R\u0026B"
                }
              ]
            },
            "weight": "1"
          },
          {
            "ID": "84282",
            "genericName": "Rap / R\u0026B Crossover",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89298",
                  "label": "Rap / R\u0026B Crossover"
                }
              ]
            },
            "weight": "1"
          }
        ],
        "tempos": [
          {
            "ID": "34094",
            "genericName": "60's",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "98",
              "hierarchyRegionName": "TEMPO-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "34283",
                  "label": "Medium Tempo"
                },
                {
                  "level": 2,
                  "descriptorID": "34290",
                  "label": "Medium"
                },
                {
                  "level": 3,
                  "descriptorID": "34311",
                  "label": "60s"
                }
              ]
            },
            "weight": "40"
          },
          {
            "ID": "34130",
            "genericName": "250's",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "98",
              "hierarchyRegionName": "TEMPO-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "43078",
                  "label": "Fast Tempo"
                },
                {
                  "level": 2,
                  "descriptorID": "34293",
                  "label": "Very Fast"
                },
                {
                  "level": 3,
                  "descriptorID": "34347",
                  "label": "250s"
                }
              ]
            },
            "weight": "34"
          },
          {
            "ID": "34108",
            "genericName": "120's",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "98",
              "hierarchyRegionName": "TEMPO-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "34283",
                  "label": "Medium Tempo"
                },
                {
                  "level": 2,
                  "descriptorID": "34291",
                  "label": "Medium Fast"
                },
                {
                  "level": 3,
                  "descriptorID": "34325",
                  "label": "120s"
                }
              ]
            },
            "weight": "25"
          }
        ]
      }
    },
    {
      "objectType": "Track",
      "trackName": "For The Night (Featuring Lil Baby, DaBaby)",
      "album": {
        "albumName": "Trending Now Volume 21",
        "releaseType": "Commercial - Multi Artist Collection"
      },
      "artist": {
        "artistName": "Various Artists"
      },
      "sonicDescriptors": {
        "moods": [
          {
            "ID": "90018",
            "genericName": "Edgy Slow Sensual Groove",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91144",
                  "label": "Sensual"
                },
                {
                  "level": 2,
                  "descriptorID": "91286",
                  "label": "Intimate"
                }
              ]
            },
            "weight": "34"
          },
          {
            "ID": "90019",
            "genericName": "Serious Upfront Expressive Sensual Beats",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91144",
                  "label": "Sensual"
                },
                {
                  "level": 2,
                  "descriptorID": "91286",
                  "label": "Intimate"
                }
              ]
            },
            "weight": "25"
          },
          {
            "ID": "34197",
            "genericName": "Dark Groovy / Savvy",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91308",
                  "label": "Dark Groovy"
                }
              ]
            },
            "weight": "16"
          },
          {
            "ID": "34193",
            "genericName": "Cool Confident Wary",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91311",
                  "label": "Wary / Defiant"
                }
              ]
            },
            "weight": "6"
          },
          {
            "ID": "90020",
            "genericName": "Expressive Pulsing Desirous Groove",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91144",
                  "label": "Sensual"
                },
                {
                  "level": 2,
                  "descriptorID": "91286",
                  "label": "Intimate"
                }
              ]
            },
            "weight": "5"
          },
          {
            "ID": "90041",
            "genericName": "Dark Strolling Edgy Cool Confessional",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91311",
                  "label": "Wary / Defiant"
                }
              ]
            },
            "weight": "5"
          },
          {
            "ID": "90028",
            "genericName": "Hurt, Caring, Pride, Perseverance \u0026 Hope",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91295",
                  "label": "Cool Confidence"
                }
              ]
            },
            "weight": "4"
          },
          {
            "ID": "90031",
            "genericName": "Sophisticated Cool Suave Empowered Groove",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91295",
                  "label": "Cool Confidence"
                }
              ]
            },
            "weight": "2"
          },
          {
            "ID": "90029",
            "genericName": "Kick-Back Dreamy Straightforward",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91295",
                  "label": "Cool Confidence"
                }
              ]
            },
            "weight": "2"
          },
          {
            "ID": "90038",
            "genericName": "Grim Unvarnished Truth",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91311",
                  "label": "Wary / Defiant"
                }
              ]
            },
            "weight": "1"
          }
        ],
        "styles": [
          {
            "ID": "84426",
            "genericName": "Mumble Rap",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89300",
                  "label": "Trap"
                }
              ]
            },
            "weight": "48"
          },
          {
            "ID": "88071",
            "genericName": "Trapsoul",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88905",
                  "label": "Soul/R\u0026B"
                },
                {
                  "level": 2,
                  "descriptorID": "89366",
                  "label": "Trapsoul"
                }
              ]
            },
            "weight": "20"
          },
          {
            "ID": "88072",
            "genericName": "Sad Trapsoul",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88905",
                  "label": "Soul/R\u0026B"
                },
                {
                  "level": 2,
                  "descriptorID": "89366",
                  "label": "Trapsoul"
                }
              ]
            },
            "weight": "13"
          },
          {
            "ID": "84278",
            "genericName": "Trap",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89300",
                  "label": "Trap"
                }
              ]
            },
            "weight": "7"
          },
          {
            "ID": "84424",
            "genericName": "Cloud Rap",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89300",
                  "label": "Trap"
                }
              ]
            },
            "weight": "5"
          },
          {
            "ID": "88067",
            "genericName": "Emo Rap",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89300",
                  "label": "Trap"
                }
              ]
            },
            "weight": "2"
          },
          {
            "ID": "84331",
            "genericName": "Urban Contemporary: R\u0026B",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88905",
                  "label": "Soul/R\u0026B"
                },
                {
                  "level": 2,
                  "descriptorID": "89364",
                  "label": "Contemporary R\u0026B"
                }
              ]
            },
            "weight": "1"
          },
          {
            "ID": "84282",
            "genericName": "Rap / R\u0026B Crossover",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89298",
                  "label": "Rap / R\u0026B Crossover"
                }
              ]
            },
            "weight": "1"
          }
        ],
        "tempos": [
          {
            "ID": "34094",
            "genericName": "60's",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "98",
              "hierarchyRegionName": "TEMPO-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "34283",
                  "label": "Medium Tempo"
                },
                {
                  "level": 2,
                  "descriptorID": "34290",
                  "label": "Medium"
                },
                {
                  "level": 3,
                  "descriptorID": "34311",
                  "label": "60s"
                }
              ]
            },
            "weight": "41"
          },
          {
            "ID": "34130",
            "genericName": "250's",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "98",
              "hierarchyRegionName": "TEMPO-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "43078",
                  "label": "Fast Tempo"
                },
                {
                  "level": 2,
                  "descriptorID": "34293",
                  "label": "Very Fast"
                },
                {
                  "level": 3,
                  "descriptorID": "34347",
                  "label": "250s"
                }
              ]
            },
            "weight": "35"
          },
          {
            "ID": "34108",
            "genericName": "120's",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "98",
              "hierarchyRegionName": "TEMPO-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "34283",
                  "label": "Medium Tempo"
                },
                {
                  "level": 2,
                  "descriptorID": "34291",
                  "label": "Medium Fast"
                },
                {
                  "level": 3,
                  "descriptorID": "34325",
                  "label": "120s"
                }
              ]
            },
            "weight": "24"
          }
        ]
      }
    },
    {
      "objectType": "Track",
      "trackName": "For The Night (Featuring Lil Baby, DaBaby)",
      "album": {
        "albumName": "2021",
        "releaseType": "Commercial - Multi Artist Collection"
      },
      "artist": {
        "artistName": "Various Artists"
      },
      "sonicDescriptors": {
        "moods": [
          {
            "ID": "90018",
            "genericName": "Edgy Slow Sensual Groove",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91144",
                  "label": "Sensual"
                },
                {
                  "level": 2,
                  "descriptorID": "91286",
                  "label": "Intimate"
                }
              ]
            },
            "weight": "30"
          },
          {
            "ID": "90019",
            "genericName": "Serious Upfront Expressive Sensual Beats",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91144",
                  "label": "Sensual"
                },
                {
                  "level": 2,
                  "descriptorID": "91286",
                  "label": "Intimate"
                }
              ]
            },
            "weight": "18"
          },
          {
            "ID": "34197",
            "genericName": "Dark Groovy / Savvy",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91308",
                  "label": "Dark Groovy"
                }
              ]
            },
            "weight": "18"
          },
          {
            "ID": "34193",
            "genericName": "Cool Confident Wary",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91311",
                  "label": "Wary / Defiant"
                }
              ]
            },
            "weight": "7"
          },
          {
            "ID": "90028",
            "genericName": "Hurt, Caring, Pride, Perseverance \u0026 Hope",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91295",
                  "label": "Cool Confidence"
                }
              ]
            },
            "weight": "7"
          },
          {
            "ID": "90041",
            "genericName": "Dark Strolling Edgy Cool Confessional",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91311",
                  "label": "Wary / Defiant"
                }
              ]
            },
            "weight": "6"
          },
          {
            "ID": "90020",
            "genericName": "Expressive Pulsing Desirous Groove",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91144",
                  "label": "Sensual"
                },
                {
                  "level": 2,
                  "descriptorID": "91286",
                  "label": "Intimate"
                }
              ]
            },
            "weight": "4"
          },
          {
            "ID": "90038",
            "genericName": "Grim Unvarnished Truth",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91311",
                  "label": "Wary / Defiant"
                }
              ]
            },
            "weight": "4"
          },
          {
            "ID": "90209",
            "genericName": "Epic Dark Serious / Building Hope",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91158",
                  "label": "Empowering"
                },
                {
                  "level": 2,
                  "descriptorID": "91532",
                  "label": "Idealistic / Stirring"
                }
              ]
            },
            "weight": "2"
          },
          {
            "ID": "90029",
            "genericName": "Kick-Back Dreamy Straightforward",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91295",
                  "label": "Cool Confidence"
                }
              ]
            },
            "weight": "2"
          }
        ],
        "styles": [
          {
            "ID": "84426",
            "genericName": "Mumble Rap",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89300",
                  "label": "Trap"
                }
              ]
            },
            "weight": "45"
          },
          {
            "ID": "88071",
            "genericName": "Trapsoul",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88905",
                  "label": "Soul/R\u0026B"
                },
                {
                  "level": 2,
                  "descriptorID": "89366",
                  "label": "Trapsoul"
                }
              ]
            },
            "weight": "22"
          },
          {
            "ID": "88072",
            "genericName": "Sad Trapsoul",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88905",
                  "label": "Soul/R\u0026B"
                },
                {
                  "level": 2,
                  "descriptorID": "89366",
                  "label": "Trapsoul"
                }
              ]
            },
            "weight": "14"
          },
          {
            "ID": "84278",
            "genericName": "Trap",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89300",
                  "label": "Trap"
                }
              ]
            },
            "weight": "7"
          },
          {
            "ID": "84424",
            "genericName": "Cloud Rap",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89300",
                  "label": "Trap"
                }
              ]
            },
            "weight": "6"
          },
          {
            "ID": "88067",
            "genericName": "Emo Rap",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89300",
                  "label": "Trap"
                }
              ]
            },
            "weight": "2"
          },
          {
            "ID": "84331",
            "genericName": "Urban Contemporary: R\u0026B",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88905",
                  "label": "Soul/R\u0026B"
                },
                {
                  "level": 2,
                  "descriptorID": "89364",
                  "label": "Contemporary R\u0026B"
                }
              ]
            },
            "weight": "1"
          },
          {
            "ID": "84282",
            "genericName": "Rap / R\u0026B Crossover",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89298",
                  "label": "Rap / R\u0026B Crossover"
                }
              ]
            },
            "weight": "1"
          }
        ],
        "tempos": [
          {
            "ID": "34094",
            "genericName": "60's",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "98",
              "hierarchyRegionName": "TEMPO-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "34283",
                  "label": "Medium Tempo"
                },
                {
                  "level": 2,
                  "descriptorID": "34290",
                  "label": "Medium"
                },
                {
                  "level": 3,
                  "descriptorID": "34311",
                  "label": "60s"
                }
              ]
            },
            "weight": "40"
          },
          {
            "ID": "34130",
            "genericName": "250's",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "98",
              "hierarchyRegionName": "TEMPO-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "43078",
                  "label": "Fast Tempo"
                },
                {
                  "level": 2,
                  "descriptorID": "34293",
                  "label": "Very Fast"
                },
                {
                  "level": 3,
                  "descriptorID": "34347",
                  "label": "250s"
                }
              ]
            },
            "weight": "34"
          },
          {
            "ID": "34108",
            "genericName": "120's",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "98",
              "hierarchyRegionName": "TEMPO-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "34283",
                  "label": "Medium Tempo"
                },
                {
                  "level": 2,
                  "descriptorID": "34291",
                  "label": "Medium Fast"
                },
                {
                  "level": 3,
                  "descriptorID": "34325",
                  "label": "120s"
                }
              ]
            },
            "weight": "25"
          }
        ]
      }
    },
    {
      "objectType": "Track",
      "trackName": "For The Night (Featuring Lil Baby, DaBaby)",
      "album": {
        "albumName": "Gaming Rap Mix",
        "releaseType": "Commercial - Multi Artist Collection"
      },
      "artist": {
        "artistName": "Various Artists"
      },
      "sonicDescriptors": {
        "moods": [
          {
            "ID": "90018",
            "genericName": "Edgy Slow Sensual Groove",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91144",
                  "label": "Sensual"
                },
                {
                  "level": 2,
                  "descriptorID": "91286",
                  "label": "Intimate"
                }
              ]
            },
            "weight": "45"
          },
          {
            "ID": "90019",
            "genericName": "Serious Upfront Expressive Sensual Beats",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91144",
                  "label": "Sensual"
                },
                {
                  "level": 2,
                  "descriptorID": "91286",
                  "label": "Intimate"
                }
              ]
            },
            "weight": "30"
          },
          {
            "ID": "34197",
            "genericName": "Dark Groovy / Savvy",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91308",
                  "label": "Dark Groovy"
                }
              ]
            },
            "weight": "8"
          },
          {
            "ID": "90020",
            "genericName": "Expressive Pulsing Desirous Groove",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91144",
                  "label": "Sensual"
                },
                {
                  "level": 2,
                  "descriptorID": "91286",
                  "label": "Intimate"
                }
              ]
            },
            "weight": "5"
          },
          {
            "ID": "90041",
            "genericName": "Dark Strolling Edgy Cool Confessional",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91311",
                  "label": "Wary / Defiant"
                }
              ]
            },
            "weight": "5"
          },
          {
            "ID": "90031",
            "genericName": "Sophisticated Cool Suave Empowered Groove",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91295",
                  "label": "Cool Confidence"
                }
              ]
            },
            "weight": "3"
          },
          {
            "ID": "34193",
            "genericName": "Cool Confident Wary",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91311",
                  "label": "Wary / Defiant"
                }
              ]
            },
            "weight": "1"
          },
          {
            "ID": "90078",
            "genericName": "Intimate Wistful Jaunty",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91148",
                  "label": "Melancholy"
                },
                {
                  "level": 2,
                  "descriptorID": "91360",
                  "label": "Light Melancholy"
                }
              ]
            },
            "weight": "1"
          },
          {
            "ID": "90028",
            "genericName": "Hurt, Caring, Pride, Perseverance \u0026 Hope",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91295",
                  "label": "Cool Confidence"
                }
              ]
            },
            "weight": "1"
          },
          {
            "ID": "90196",
            "genericName": "Edgy Soulful Rhythmic",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91157",
                  "label": "Energizing"
                },
                {
                  "level": 2,
                  "descriptorID": "91516",
                  "label": "Edgy / Sexy"
                }
              ]
            },
            "weight": "1"
          }
        ],
        "styles": [
          {
            "ID": "88071",
            "genericName": "Trapsoul",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88905",
                  "label": "Soul/R\u0026B"
                },
                {
                  "level": 2,
                  "descriptorID": "89366",
                  "label": "Trapsoul"
                }
              ]
            },
            "weight": "38"
          },
          {
            "ID": "84426",
            "genericName": "Mumble Rap",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89300",
                  "label": "Trap"
                }
              ]
            },
            "weight": "28"
          },
          {
            "ID": "88072",
            "genericName": "Sad Trapsoul",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88905",
                  "label": "Soul/R\u0026B"
                },
                {
                  "level": 2,
                  "descriptorID": "89366",
                  "label": "Trapsoul"
                }
              ]
            },
            "weight": "17"
          },
          {
            "ID": "84424",
            "genericName": "Cloud Rap",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89300",
                  "label": "Trap"
                }
              ]
            },
            "weight": "5"
          },
          {
            "ID": "84278",
            "genericName": "Trap",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89300",
                  "label": "Trap"
                }
              ]
            },
            "weight": "4"
          },
          {
            "ID": "88067",
            "genericName": "Emo Rap",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89300",
                  "label": "Trap"
                }
              ]
            },
            "weight": "2"
          },
          {
            "ID": "84331",
            "genericName": "Urban Contemporary: R\u0026B",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88905",
                  "label": "Soul/R\u0026B"
                },
                {
                  "level": 2,
                  "descriptorID": "89364",
                  "label": "Contemporary R\u0026B"
                }
              ]
            },
            "weight": "2"
          },
          {
            "ID": "88074",
            "genericName": "Urban Crossover: Bass",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88905",
                  "label": "Soul/R\u0026B"
                },
                {
                  "level": 2,
                  "descriptorID": "89359",
                  "label": "Urban Crossover"
                }
              ]
            },
            "weight": "1"
          },
          {
            "ID": "84282",
            "genericName": "Rap / R\u0026B Crossover",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89298",
                  "label": "Rap / R\u0026B Crossover"
                }
              ]
            },
            "weight": "1"
          }
        ],
        "tempos": [
          {
            "ID": "34094",
            "genericName": "60's",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "98",
              "hierarchyRegionName": "TEMPO-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "34283",
                  "label": "Medium Tempo"
                },
                {
                  "level": 2,
                  "descriptorID": "34290",
                  "label": "Medium"
                },
                {
                  "level": 3,
                  "descriptorID": "34311",
                  "label": "60s"
                }
              ]
            },
            "weight": "40"
          },
          {
            "ID": "34130",
            "genericName": "250's",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "98",
              "hierarchyRegionName": "TEMPO-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "43078",
                  "label": "Fast Tempo"
                },
                {
                  "level": 2,
                  "descriptorID": "34293",
                  "label": "Very Fast"
                },
                {
                  "level": 3,
                  "descriptorID": "34347",
                  "label": "250s"
                }
              ]
            },
            "weight": "34"
          },
          {
            "ID": "34108",
            "genericName": "120's",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "98",
              "hierarchyRegionName": "TEMPO-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "34283",
                  "label": "Medium Tempo"
                },
                {
                  "level": 2,
                  "descriptorID": "34291",
                  "label": "Medium Fast"
                },
                {
                  "level": 3,
                  "descriptorID": "34325",
                  "label": "120s"
                }
              ]
            },
            "weight": "25"
          }
        ]
      }
    },
    {
      "objectType": "Track",
      "trackName": "For The Night (Featuring Lil Baby, DaBaby)",
      "album": {
        "albumName": "Rap Hits 2021",
        "releaseType": "Commercial - Multi Artist Collection"
      },
      "artist": {
        "artistName": "Various Artists"
      },
      "sonicDescriptors": {
        "moods": [
          {
            "ID": "90018",
            "genericName": "Edgy Slow Sensual Groove",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91144",
                  "label": "Sensual"
                },
                {
                  "level": 2,
                  "descriptorID": "91286",
                  "label": "Intimate"
                }
              ]
            },
            "weight": "45"
          },
          {
            "ID": "90019",
            "genericName": "Serious Upfront Expressive Sensual Beats",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91144",
                  "label": "Sensual"
                },
                {
                  "level": 2,
                  "descriptorID": "91286",
                  "label": "Intimate"
                }
              ]
            },
            "weight": "30"
          },
          {
            "ID": "34197",
            "genericName": "Dark Groovy / Savvy",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91308",
                  "label": "Dark Groovy"
                }
              ]
            },
            "weight": "8"
          },
          {
            "ID": "90020",
            "genericName": "Expressive Pulsing Desirous Groove",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91144",
                  "label": "Sensual"
                },
                {
                  "level": 2,
                  "descriptorID": "91286",
                  "label": "Intimate"
                }
              ]
            },
            "weight": "5"
          },
          {
            "ID": "90041",
            "genericName": "Dark Strolling Edgy Cool Confessional",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91311",
                  "label": "Wary / Defiant"
                }
              ]
            },
            "weight": "5"
          },
          {
            "ID": "90031",
            "genericName": "Sophisticated Cool Suave Empowered Groove",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91295",
                  "label": "Cool Confidence"
                }
              ]
            },
            "weight": "3"
          },
          {
            "ID": "34193",
            "genericName": "Cool Confident Wary",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91311",
                  "label": "Wary / Defiant"
                }
              ]
            },
            "weight": "1"
          },
          {
            "ID": "90078",
            "genericName": "Intimate Wistful Jaunty",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91148",
                  "label": "Melancholy"
                },
                {
                  "level": 2,
                  "descriptorID": "91360",
                  "label": "Light Melancholy"
                }
              ]
            },
            "weight": "1"
          },
          {
            "ID": "90028",
            "genericName": "Hurt, Caring, Pride, Perseverance \u0026 Hope",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91295",
                  "label": "Cool Confidence"
                }
              ]
            },
            "weight": "1"
          },
          {
            "ID": "90196",
            "genericName": "Edgy Soulful Rhythmic",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91157",
                  "label": "Energizing"
                },
                {
                  "level": 2,
                  "descriptorID": "91516",
                  "label": "Edgy / Sexy"
                }
              ]
            },
            "weight": "1"
          }
        ],
        "styles": [
          {
            "ID": "88071",
            "genericName": "Trapsoul",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88905",
                  "label": "Soul/R\u0026B"
                },
                {
                  "level": 2,
                  "descriptorID": "89366",
                  "label": "Trapsoul"
                }
              ]
            },
            "weight": "38"
          },
          {
            "ID": "84426",
            "genericName": "Mumble Rap",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89300",
                  "label": "Trap"
                }
              ]
            },
            "weight": "28"
          },
          {
            "ID": "88072",
            "genericName": "Sad Trapsoul",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88905",
                  "label": "Soul/R\u0026B"
                },
                {
                  "level": 2,
                  "descriptorID": "89366",
                  "label": "Trapsoul"
                }
              ]
            },
            "weight": "17"
          },
          {
            "ID": "84424",
            "genericName": "Cloud Rap",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89300",
                  "label": "Trap"
                }
              ]
            },
            "weight": "5"
          },
          {
            "ID": "84278",
            "genericName": "Trap",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89300",
                  "label": "Trap"
                }
              ]
            },
            "weight": "4"
          },
          {
            "ID": "88067",
            "genericName": "Emo Rap",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89300",
                  "label": "Trap"
                }
              ]
            },
            "weight": "2"
          },
          {
            "ID": "84331",
            "genericName": "Urban Contemporary: R\u0026B",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88905",
                  "label": "Soul/R\u0026B"
                },
                {
                  "level": 2,
                  "descriptorID": "89364",
                  "label": "Contemporary R\u0026B"
                }
              ]
            },
            "weight": "2"
          },
          {
            "ID": "88074",
            "genericName": "Urban Crossover: Bass",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88905",
                  "label": "Soul/R\u0026B"
                },
                {
                  "level": 2,
                  "descriptorID": "89359",
                  "label": "Urban Crossover"
                }
              ]
            },
            "weight": "1"
          },
          {
            "ID": "84282",
            "genericName": "Rap / R\u0026B Crossover",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89298",
                  "label": "Rap / R\u0026B Crossover"
                }
              ]
            },
            "weight": "1"
          }
        ],
        "tempos": [
          {
            "ID": "34094",
            "genericName": "60's",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "98",
              "hierarchyRegionName": "TEMPO-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "34283",
                  "label": "Medium Tempo"
                },
                {
                  "level": 2,
                  "descriptorID": "34290",
                  "label": "Medium"
                },
                {
                  "level": 3,
                  "descriptorID": "34311",
                  "label": "60s"
                }
              ]
            },
            "weight": "40"
          },
          {
            "ID": "34130",
            "genericName": "250's",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "98",
              "hierarchyRegionName": "TEMPO-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "43078",
                  "label": "Fast Tempo"
                },
                {
                  "level": 2,
                  "descriptorID": "34293",
                  "label": "Very Fast"
                },
                {
                  "level": 3,
                  "descriptorID": "34347",
                  "label": "250s"
                }
              ]
            },
            "weight": "34"
          },
          {
            "ID": "34108",
            "genericName": "120's",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "98",
              "hierarchyRegionName": "TEMPO-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "34283",
                  "label": "Medium Tempo"
                },
                {
                  "level": 2,
                  "descriptorID": "34291",
                  "label": "Medium Fast"
                },
                {
                  "level": 3,
                  "descriptorID": "34325",
                  "label": "120s"
                }
              ]
            },
            "weight": "25"
          }
        ]
      }
    },
    {
      "objectType": "Track",
      "trackName": "For The Night (Featuring Lil Baby, DaBaby)",
      "album": {
        "albumName": "Hits 2021",
        "releaseType": "Commercial - Multi Artist Collection"
      },
      "artist": {
        "artistName": "Various Artists"
      },
      "sonicDescriptors": {
        "moods": [
          {
            "ID": "90018",
            "genericName": "Edgy Slow Sensual Groove",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91144",
                  "label": "Sensual"
                },
                {
                  "level": 2,
                  "descriptorID": "91286",
                  "label": "Intimate"
                }
              ]
            },
            "weight": "45"
          },
          {
            "ID": "90019",
            "genericName": "Serious Upfront Expressive Sensual Beats",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91144",
                  "label": "Sensual"
                },
                {
                  "level": 2,
                  "descriptorID": "91286",
                  "label": "Intimate"
                }
              ]
            },
            "weight": "30"
          },
          {
            "ID": "34197",
            "genericName": "Dark Groovy / Savvy",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91308",
                  "label": "Dark Groovy"
                }
              ]
            },
            "weight": "8"
          },
          {
            "ID": "90020",
            "genericName": "Expressive Pulsing Desirous Groove",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91144",
                  "label": "Sensual"
                },
                {
                  "level": 2,
                  "descriptorID": "91286",
                  "label": "Intimate"
                }
              ]
            },
            "weight": "5"
          },
          {
            "ID": "90041",
            "genericName": "Dark Strolling Edgy Cool Confessional",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91311",
                  "label": "Wary / Defiant"
                }
              ]
            },
            "weight": "5"
          },
          {
            "ID": "90031",
            "genericName": "Sophisticated Cool Suave Empowered Groove",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91295",
                  "label": "Cool Confidence"
                }
              ]
            },
            "weight": "3"
          },
          {
            "ID": "34193",
            "genericName": "Cool Confident Wary",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91311",
                  "label": "Wary / Defiant"
                }
              ]
            },
            "weight": "1"
          },
          {
            "ID": "90078",
            "genericName": "Intimate Wistful Jaunty",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91148",
                  "label": "Melancholy"
                },
                {
                  "level": 2,
                  "descriptorID": "91360",
                  "label": "Light Melancholy"
                }
              ]
            },
            "weight": "1"
          },
          {
            "ID": "90028",
            "genericName": "Hurt, Caring, Pride, Perseverance \u0026 Hope",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91295",
                  "label": "Cool Confidence"
                }
              ]
            },
            "weight": "1"
          },
          {
            "ID": "90196",
            "genericName": "Edgy Soulful Rhythmic",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91157",
                  "label": "Energizing"
                },
                {
                  "level": 2,
                  "descriptorID": "91516",
                  "label": "Edgy / Sexy"
                }
              ]
            },
            "weight": "1"
          }
        ],
        "styles": [
          {
            "ID": "88071",
            "genericName": "Trapsoul",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88905",
                  "label": "Soul/R\u0026B"
                },
                {
                  "level": 2,
                  "descriptorID": "89366",
                  "label": "Trapsoul"
                }
              ]
            },
            "weight": "38"
          },
          {
            "ID": "84426",
            "genericName": "Mumble Rap",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89300",
                  "label": "Trap"
                }
              ]
            },
            "weight": "28"
          },
          {
            "ID": "88072",
            "genericName": "Sad Trapsoul",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88905",
                  "label": "Soul/R\u0026B"
                },
                {
                  "level": 2,
                  "descriptorID": "89366",
                  "label": "Trapsoul"
                }
              ]
            },
            "weight": "17"
          },
          {
            "ID": "84424",
            "genericName": "Cloud Rap",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89300",
                  "label": "Trap"
                }
              ]
            },
            "weight": "5"
          },
          {
            "ID": "84278",
            "genericName": "Trap",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89300",
                  "label": "Trap"
                }
              ]
            },
            "weight": "4"
          },
          {
            "ID": "88067",
            "genericName": "Emo Rap",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89300",
                  "label": "Trap"
                }
              ]
            },
            "weight": "2"
          },
          {
            "ID": "84331",
            "genericName": "Urban Contemporary: R\u0026B",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88905",
                  "label": "Soul/R\u0026B"
                },
                {
                  "level": 2,
                  "descriptorID": "89364",
                  "label": "Contemporary R\u0026B"
                }
              ]
            },
            "weight": "2"
          },
          {
            "ID": "88074",
            "genericName": "Urban Crossover: Bass",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88905",
                  "label": "Soul/R\u0026B"
                },
                {
                  "level": 2,
                  "descriptorID": "89359",
                  "label": "Urban Crossover"
                }
              ]
            },
            "weight": "1"
          },
          {
            "ID": "84282",
            "genericName": "Rap / R\u0026B Crossover",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89298",
                  "label": "Rap / R\u0026B Crossover"
                }
              ]
            },
            "weight": "1"
          }
        ],
        "tempos": [
          {
            "ID": "34094",
            "genericName": "60's",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "98",
              "hierarchyRegionName": "TEMPO-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "34283",
                  "label": "Medium Tempo"
                },
                {
                  "level": 2,
                  "descriptorID": "34290",
                  "label": "Medium"
                },
                {
                  "level": 3,
                  "descriptorID": "34311",
                  "label": "60s"
                }
              ]
            },
            "weight": "40"
          },
          {
            "ID": "34130",
            "genericName": "250's",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "98",
              "hierarchyRegionName": "TEMPO-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "43078",
                  "label": "Fast Tempo"
                },
                {
                  "level": 2,
                  "descriptorID": "34293",
                  "label": "Very Fast"
                },
                {
                  "level": 3,
                  "descriptorID": "34347",
                  "label": "250s"
                }
              ]
            },
            "weight": "34"
          },
          {
            "ID": "34108",
            "genericName": "120's",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "98",
              "hierarchyRegionName": "TEMPO-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "34283",
                  "label": "Medium Tempo"
                },
                {
                  "level": 2,
                  "descriptorID": "34291",
                  "label": "Medium Fast"
                },
                {
                  "level": 3,
                  "descriptorID": "34325",
                  "label": "120s"
                }
              ]
            },
            "weight": "25"
          }
        ]
      }
    },
    {
      "objectType": "Track",
      "trackName": "For The Night (Featuring Lil Baby, DaBaby)",
      "album": {
        "albumName": "Hits Brasil 2021",
        "releaseType": "Commercial - Multi Artist Collection"
      },
      "artist": {
        "artistName": "Various Artists"
      },
      "sonicDescriptors": {
        "moods": [
          {
            "ID": "90018",
            "genericName": "Edgy Slow Sensual Groove",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91144",
                  "label": "Sensual"
                },
                {
                  "level": 2,
                  "descriptorID": "91286",
                  "label": "Intimate"
                }
              ]
            },
            "weight": "45"
          },
          {
            "ID": "90019",
            "genericName": "Serious Upfront Expressive Sensual Beats",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91144",
                  "label": "Sensual"
                },
                {
                  "level": 2,
                  "descriptorID": "91286",
                  "label": "Intimate"
                }
              ]
            },
            "weight": "30"
          },
          {
            "ID": "34197",
            "genericName": "Dark Groovy / Savvy",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91308",
                  "label": "Dark Groovy"
                }
              ]
            },
            "weight": "8"
          },
          {
            "ID": "90020",
            "genericName": "Expressive Pulsing Desirous Groove",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91144",
                  "label": "Sensual"
                },
                {
                  "level": 2,
                  "descriptorID": "91286",
                  "label": "Intimate"
                }
              ]
            },
            "weight": "5"
          },
          {
            "ID": "90041",
            "genericName": "Dark Strolling Edgy Cool Confessional",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91311",
                  "label": "Wary / Defiant"
                }
              ]
            },
            "weight": "5"
          },
          {
            "ID": "90031",
            "genericName": "Sophisticated Cool Suave Empowered Groove",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91295",
                  "label": "Cool Confidence"
                }
              ]
            },
            "weight": "3"
          },
          {
            "ID": "34193",
            "genericName": "Cool Confident Wary",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91311",
                  "label": "Wary / Defiant"
                }
              ]
            },
            "weight": "1"
          },
          {
            "ID": "90078",
            "genericName": "Intimate Wistful Jaunty",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91148",
                  "label": "Melancholy"
                },
                {
                  "level": 2,
                  "descriptorID": "91360",
                  "label": "Light Melancholy"
                }
              ]
            },
            "weight": "1"
          },
          {
            "ID": "90028",
            "genericName": "Hurt, Caring, Pride, Perseverance \u0026 Hope",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91295",
                  "label": "Cool Confidence"
                }
              ]
            },
            "weight": "1"
          },
          {
            "ID": "90196",
            "genericName": "Edgy Soulful Rhythmic",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91157",
                  "label": "Energizing"
                },
                {
                  "level": 2,
                  "descriptorID": "91516",
                  "label": "Edgy / Sexy"
                }
              ]
            },
            "weight": "1"
          }
        ],
        "styles": [
          {
            "ID": "88071",
            "genericName": "Trapsoul",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88905",
                  "label": "Soul/R\u0026B"
                },
                {
                  "level": 2,
                  "descriptorID": "89366",
                  "label": "Trapsoul"
                }
              ]
            },
            "weight": "38"
          },
          {
            "ID": "84426",
            "genericName": "Mumble Rap",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89300",
                  "label": "Trap"
                }
              ]
            },
            "weight": "28"
          },
          {
            "ID": "88072",
            "genericName": "Sad Trapsoul",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88905",
                  "label": "Soul/R\u0026B"
                },
                {
                  "level": 2,
                  "descriptorID": "89366",
                  "label": "Trapsoul"
                }
              ]
            },
            "weight": "17"
          },
          {
            "ID": "84424",
            "genericName": "Cloud Rap",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89300",
                  "label": "Trap"
                }
              ]
            },
            "weight": "5"
          },
          {
            "ID": "84278",
            "genericName": "Trap",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89300",
                  "label": "Trap"
                }
              ]
            },
            "weight": "4"
          },
          {
            "ID": "88067",
            "genericName": "Emo Rap",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89300",
                  "label": "Trap"
                }
              ]
            },
            "weight": "2"
          },
          {
            "ID": "84331",
            "genericName": "Urban Contemporary: R\u0026B",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88905",
                  "label": "Soul/R\u0026B"
                },
                {
                  "level": 2,
                  "descriptorID": "89364",
                  "label": "Contemporary R\u0026B"
                }
              ]
            },
            "weight": "2"
          },
          {
            "ID": "88074",
            "genericName": "Urban Crossover: Bass",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88905",
                  "label": "Soul/R\u0026B"
                },
                {
                  "level": 2,
                  "descriptorID": "89359",
                  "label": "Urban Crossover"
                }
              ]
            },
            "weight": "1"
          },
          {
            "ID": "84282",
            "genericName": "Rap / R\u0026B Crossover",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89298",
                  "label": "Rap / R\u0026B Crossover"
                }
              ]
            },
            "weight": "1"
          }
        ],
        "tempos": [
          {
            "ID": "34094",
            "genericName": "60's",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "98",
              "hierarchyRegionName": "TEMPO-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "34283",
                  "label": "Medium Tempo"
                },
                {
                  "level": 2,
                  "descriptorID": "34290",
                  "label": "Medium"
                },
                {
                  "level": 3,
                  "descriptorID": "34311",
                  "label": "60s"
                }
              ]
            },
            "weight": "40"
          },
          {
            "ID": "34130",
            "genericName": "250's",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "98",
              "hierarchyRegionName": "TEMPO-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "43078",
                  "label": "Fast Tempo"
                },
                {
                  "level": 2,
                  "descriptorID": "34293",
                  "label": "Very Fast"
                },
                {
                  "level": 3,
                  "descriptorID": "34347",
                  "label": "250s"
                }
              ]
            },
            "weight": "34"
          },
          {
            "ID": "34108",
            "genericName": "120's",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "98",
              "hierarchyRegionName": "TEMPO-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "34283",
                  "label": "Medium Tempo"
                },
                {
                  "level": 2,
                  "descriptorID": "34291",
                  "label": "Medium Fast"
                },
                {
                  "level": 3,
                  "descriptorID": "34325",
                  "label": "120s"
                }
              ]
            },
            "weight": "25"
          }
        ]
      }
    },
    {
      "objectType": "Track",
      "trackName": "For The Night (Featuring Lil Baby, DaBaby)",
      "album": {
        "albumName": "Hip-Hop Summer 2021",
        "releaseType": "Unclassified"
      },
      "artist": {
        "artistName": "Various Artists"
      },
      "sonicDescriptors": {
        "moods": [
          {
            "ID": "90018",
            "genericName": "Edgy Slow Sensual Groove",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91144",
                  "label": "Sensual"
                },
                {
                  "level": 2,
                  "descriptorID": "91286",
                  "label": "Intimate"
                }
              ]
            },
            "weight": "33"
          },
          {
            "ID": "90019",
            "genericName": "Serious Upfront Expressive Sensual Beats",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91144",
                  "label": "Sensual"
                },
                {
                  "level": 2,
                  "descriptorID": "91286",
                  "label": "Intimate"
                }
              ]
            },
            "weight": "20"
          },
          {
            "ID": "34197",
            "genericName": "Dark Groovy / Savvy",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91308",
                  "label": "Dark Groovy"
                }
              ]
            },
            "weight": "17"
          },
          {
            "ID": "34193",
            "genericName": "Cool Confident Wary",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91311",
                  "label": "Wary / Defiant"
                }
              ]
            },
            "weight": "7"
          },
          {
            "ID": "90041",
            "genericName": "Dark Strolling Edgy Cool Confessional",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91311",
                  "label": "Wary / Defiant"
                }
              ]
            },
            "weight": "6"
          },
          {
            "ID": "90028",
            "genericName": "Hurt, Caring, Pride, Perseverance \u0026 Hope",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91295",
                  "label": "Cool Confidence"
                }
              ]
            },
            "weight": "5"
          },
          {
            "ID": "90020",
            "genericName": "Expressive Pulsing Desirous Groove",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91144",
                  "label": "Sensual"
                },
                {
                  "level": 2,
                  "descriptorID": "91286",
                  "label": "Intimate"
                }
              ]
            },
            "weight": "4"
          },
          {
            "ID": "90038",
            "genericName": "Grim Unvarnished Truth",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91311",
                  "label": "Wary / Defiant"
                }
              ]
            },
            "weight": "2"
          },
          {
            "ID": "90031",
            "genericName": "Sophisticated Cool Suave Empowered Groove",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91295",
                  "label": "Cool Confidence"
                }
              ]
            },
            "weight": "2"
          },
          {
            "ID": "90029",
            "genericName": "Kick-Back Dreamy Straightforward",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91295",
                  "label": "Cool Confidence"
                }
              ]
            },
            "weight": "2"
          }
        ],
        "styles": [
          {
            "ID": "84426",
            "genericName": "Mumble Rap",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89300",
                  "label": "Trap"
                }
              ]
            },
            "weight": "44"
          },
          {
            "ID": "88071",
            "genericName": "Trapsoul",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88905",
                  "label": "Soul/R\u0026B"
                },
                {
                  "level": 2,
                  "descriptorID": "89366",
                  "label": "Trapsoul"
                }
              ]
            },
            "weight": "22"
          },
          {
            "ID": "88072",
            "genericName": "Sad Trapsoul",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88905",
                  "label": "Soul/R\u0026B"
                },
                {
                  "level": 2,
                  "descriptorID": "89366",
                  "label": "Trapsoul"
                }
              ]
            },
            "weight": "14"
          },
          {
            "ID": "84278",
            "genericName": "Trap",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89300",
                  "label": "Trap"
                }
              ]
            },
            "weight": "7"
          },
          {
            "ID": "84424",
            "genericName": "Cloud Rap",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89300",
                  "label": "Trap"
                }
              ]
            },
            "weight": "6"
          },
          {
            "ID": "88067",
            "genericName": "Emo Rap",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89300",
                  "label": "Trap"
                }
              ]
            },
            "weight": "2"
          },
          {
            "ID": "84331",
            "genericName": "Urban Contemporary: R\u0026B",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88905",
                  "label": "Soul/R\u0026B"
                },
                {
                  "level": 2,
                  "descriptorID": "89364",
                  "label": "Contemporary R\u0026B"
                }
              ]
            },
            "weight": "1"
          },
          {
            "ID": "84282",
            "genericName": "Rap / R\u0026B Crossover",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89298",
                  "label": "Rap / R\u0026B Crossover"
                }
              ]
            },
            "weight": "1"
          }
        ],
        "tempos": [
          {
            "ID": "34094",
            "genericName": "60's",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "98",
              "hierarchyRegionName": "TEMPO-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "34283",
                  "label": "Medium Tempo"
                },
                {
                  "level": 2,
                  "descriptorID": "34290",
                  "label": "Medium"
                },
                {
                  "level": 3,
                  "descriptorID": "34311",
                  "label": "60s"
                }
              ]
            },
            "weight": "40"
          },
          {
            "ID": "34130",
            "genericName": "250's",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "98",
              "hierarchyRegionName": "TEMPO-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "43078",
                  "label": "Fast Tempo"
                },
                {
                  "level": 2,
                  "descriptorID": "34293",
                  "label": "Very Fast"
                },
                {
                  "level": 3,
                  "descriptorID": "34347",
                  "label": "250s"
                }
              ]
            },
            "weight": "34"
          },
          {
            "ID": "34108",
            "genericName": "120's",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "98",
              "hierarchyRegionName": "TEMPO-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "34283",
                  "label": "Medium Tempo"
                },
                {
                  "level": 2,
                  "descriptorID": "34291",
                  "label": "Medium Fast"
                },
                {
                  "level": 3,
                  "descriptorID": "34325",
                  "label": "120s"
                }
              ]
            },
            "weight": "25"
          }
        ]
      }
    },
    {
      "objectType": "Track",
      "trackName": "For The Night (Featuring Lil Baby, DaBaby)",
      "album": {
        "albumName": "New Money",
        "releaseType": "Commercial - Multi Artist Collection"
      },
      "artist": {
        "artistName": "Various Artists"
      },
      "sonicDescriptors": {
        "moods": [
          {
            "ID": "90018",
            "genericName": "Edgy Slow Sensual Groove",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91144",
                  "label": "Sensual"
                },
                {
                  "level": 2,
                  "descriptorID": "91286",
                  "label": "Intimate"
                }
              ]
            },
            "weight": "34"
          },
          {
            "ID": "90019",
            "genericName": "Serious Upfront Expressive Sensual Beats",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91144",
                  "label": "Sensual"
                },
                {
                  "level": 2,
                  "descriptorID": "91286",
                  "label": "Intimate"
                }
              ]
            },
            "weight": "24"
          },
          {
            "ID": "34197",
            "genericName": "Dark Groovy / Savvy",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91308",
                  "label": "Dark Groovy"
                }
              ]
            },
            "weight": "18"
          },
          {
            "ID": "34193",
            "genericName": "Cool Confident Wary",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91311",
                  "label": "Wary / Defiant"
                }
              ]
            },
            "weight": "6"
          },
          {
            "ID": "90020",
            "genericName": "Expressive Pulsing Desirous Groove",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91144",
                  "label": "Sensual"
                },
                {
                  "level": 2,
                  "descriptorID": "91286",
                  "label": "Intimate"
                }
              ]
            },
            "weight": "5"
          },
          {
            "ID": "90041",
            "genericName": "Dark Strolling Edgy Cool Confessional",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91311",
                  "label": "Wary / Defiant"
                }
              ]
            },
            "weight": "5"
          },
          {
            "ID": "90028",
            "genericName": "Hurt, Caring, Pride, Perseverance \u0026 Hope",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91295",
                  "label": "Cool Confidence"
                }
              ]
            },
            "weight": "4"
          },
          {
            "ID": "90031",
            "genericName": "Sophisticated Cool Suave Empowered Groove",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91295",
                  "label": "Cool Confidence"
                }
              ]
            },
            "weight": "2"
          },
          {
            "ID": "90029",
            "genericName": "Kick-Back Dreamy Straightforward",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91295",
                  "label": "Cool Confidence"
                }
              ]
            },
            "weight": "2"
          },
          {
            "ID": "90038",
            "genericName": "Grim Unvarnished Truth",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91311",
                  "label": "Wary / Defiant"
                }
              ]
            },
            "weight": "1"
          }
        ],
        "styles": [
          {
            "ID": "84426",
            "genericName": "Mumble Rap",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89300",
                  "label": "Trap"
                }
              ]
            },
            "weight": "49"
          },
          {
            "ID": "88071",
            "genericName": "Trapsoul",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88905",
                  "label": "Soul/R\u0026B"
                },
                {
                  "level": 2,
                  "descriptorID": "89366",
                  "label": "Trapsoul"
                }
              ]
            },
            "weight": "20"
          },
          {
            "ID": "88072",
            "genericName": "Sad Trapsoul",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88905",
                  "label": "Soul/R\u0026B"
                },
                {
                  "level": 2,
                  "descriptorID": "89366",
                  "label": "Trapsoul"
                }
              ]
            },
            "weight": "13"
          },
          {
            "ID": "84278",
            "genericName": "Trap",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89300",
                  "label": "Trap"
                }
              ]
            },
            "weight": "7"
          },
          {
            "ID": "84424",
            "genericName": "Cloud Rap",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89300",
                  "label": "Trap"
                }
              ]
            },
            "weight": "5"
          },
          {
            "ID": "88067",
            "genericName": "Emo Rap",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89300",
                  "label": "Trap"
                }
              ]
            },
            "weight": "2"
          },
          {
            "ID": "84331",
            "genericName": "Urban Contemporary: R\u0026B",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88905",
                  "label": "Soul/R\u0026B"
                },
                {
                  "level": 2,
                  "descriptorID": "89364",
                  "label": "Contemporary R\u0026B"
                }
              ]
            },
            "weight": "1"
          },
          {
            "ID": "84282",
            "genericName": "Rap / R\u0026B Crossover",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89298",
                  "label": "Rap / R\u0026B Crossover"
                }
              ]
            },
            "weight": "1"
          }
        ],
        "tempos": [
          {
            "ID": "34094",
            "genericName": "60's",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "98",
              "hierarchyRegionName": "TEMPO-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "34283",
                  "label": "Medium Tempo"
                },
                {
                  "level": 2,
                  "descriptorID": "34290",
                  "label": "Medium"
                },
                {
                  "level": 3,
                  "descriptorID": "34311",
                  "label": "60s"
                }
              ]
            },
            "weight": "40"
          },
          {
            "ID": "34130",
            "genericName": "250's",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "98",
              "hierarchyRegionName": "TEMPO-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "43078",
                  "label": "Fast Tempo"
                },
                {
                  "level": 2,
                  "descriptorID": "34293",
                  "label": "Very Fast"
                },
                {
                  "level": 3,
                  "descriptorID": "34347",
                  "label": "250s"
                }
              ]
            },
            "weight": "34"
          },
          {
            "ID": "34108",
            "genericName": "120's",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "98",
              "hierarchyRegionName": "TEMPO-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "34283",
                  "label": "Medium Tempo"
                },
                {
                  "level": 2,
                  "descriptorID": "34291",
                  "label": "Medium Fast"
                },
                {
                  "level": 3,
                  "descriptorID": "34325",
                  "label": "120s"
                }
              ]
            },
            "weight": "25"
          }
        ]
      }
    },
    {
      "objectType": "Track",
      "trackName": "For The Night (Featuring Lil Baby, DaBaby)",
      "album": {
        "albumName": "Spring Party 2021",
        "releaseType": "Commercial - Multi Artist Collection"
      },
      "artist": {
        "artistName": "Various Artists"
      },
      "sonicDescriptors": {
        "moods": [
          {
            "ID": "90018",
            "genericName": "Edgy Slow Sensual Groove",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91144",
                  "label": "Sensual"
                },
                {
                  "level": 2,
                  "descriptorID": "91286",
                  "label": "Intimate"
                }
              ]
            },
            "weight": "32"
          },
          {
            "ID": "90019",
            "genericName": "Serious Upfront Expressive Sensual Beats",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91144",
                  "label": "Sensual"
                },
                {
                  "level": 2,
                  "descriptorID": "91286",
                  "label": "Intimate"
                }
              ]
            },
            "weight": "18"
          },
          {
            "ID": "34197",
            "genericName": "Dark Groovy / Savvy",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91308",
                  "label": "Dark Groovy"
                }
              ]
            },
            "weight": "18"
          },
          {
            "ID": "34193",
            "genericName": "Cool Confident Wary",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91311",
                  "label": "Wary / Defiant"
                }
              ]
            },
            "weight": "7"
          },
          {
            "ID": "90028",
            "genericName": "Hurt, Caring, Pride, Perseverance \u0026 Hope",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91295",
                  "label": "Cool Confidence"
                }
              ]
            },
            "weight": "6"
          },
          {
            "ID": "90041",
            "genericName": "Dark Strolling Edgy Cool Confessional",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91311",
                  "label": "Wary / Defiant"
                }
              ]
            },
            "weight": "6"
          },
          {
            "ID": "90020",
            "genericName": "Expressive Pulsing Desirous Groove",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91144",
                  "label": "Sensual"
                },
                {
                  "level": 2,
                  "descriptorID": "91286",
                  "label": "Intimate"
                }
              ]
            },
            "weight": "5"
          },
          {
            "ID": "90029",
            "genericName": "Kick-Back Dreamy Straightforward",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91295",
                  "label": "Cool Confidence"
                }
              ]
            },
            "weight": "2"
          },
          {
            "ID": "90038",
            "genericName": "Grim Unvarnished Truth",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91311",
                  "label": "Wary / Defiant"
                }
              ]
            },
            "weight": "2"
          },
          {
            "ID": "90209",
            "genericName": "Epic Dark Serious / Building Hope",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91158",
                  "label": "Empowering"
                },
                {
                  "level": 2,
                  "descriptorID": "91532",
                  "label": "Idealistic / Stirring"
                }
              ]
            },
            "weight": "2"
          }
        ],
        "styles": [
          {
            "ID": "84426",
            "genericName": "Mumble Rap",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89300",
                  "label": "Trap"
                }
              ]
            },
            "weight": "44"
          },
          {
            "ID": "88071",
            "genericName": "Trapsoul",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88905",
                  "label": "Soul/R\u0026B"
                },
                {
                  "level": 2,
                  "descriptorID": "89366",
                  "label": "Trapsoul"
                }
              ]
            },
            "weight": "23"
          },
          {
            "ID": "88072",
            "genericName": "Sad Trapsoul",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88905",
                  "label": "Soul/R\u0026B"
                },
                {
                  "level": 2,
                  "descriptorID": "89366",
                  "label": "Trapsoul"
                }
              ]
            },
            "weight": "14"
          },
          {
            "ID": "84278",
            "genericName": "Trap",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89300",
                  "label": "Trap"
                }
              ]
            },
            "weight": "7"
          },
          {
            "ID": "84424",
            "genericName": "Cloud Rap",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89300",
                  "label": "Trap"
                }
              ]
            },
            "weight": "6"
          },
          {
            "ID": "88067",
            "genericName": "Emo Rap",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89300",
                  "label": "Trap"
                }
              ]
            },
            "weight": "2"
          },
          {
            "ID": "84331",
            "genericName": "Urban Contemporary: R\u0026B",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88905",
                  "label": "Soul/R\u0026B"
                },
                {
                  "level": 2,
                  "descriptorID": "89364",
                  "label": "Contemporary R\u0026B"
                }
              ]
            },
            "weight": "1"
          },
          {
            "ID": "84282",
            "genericName": "Rap / R\u0026B Crossover",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89298",
                  "label": "Rap / R\u0026B Crossover"
                }
              ]
            },
            "weight": "1"
          }
        ],
        "tempos": [
          {
            "ID": "34094",
            "genericName": "60's",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "98",
              "hierarchyRegionName": "TEMPO-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "34283",
                  "label": "Medium Tempo"
                },
                {
                  "level": 2,
                  "descriptorID": "34290",
                  "label": "Medium"
                },
                {
                  "level": 3,
                  "descriptorID": "34311",
                  "label": "60s"
                }
              ]
            },
            "weight": "40"
          },
          {
            "ID": "34130",
            "genericName": "250's",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "98",
              "hierarchyRegionName": "TEMPO-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "43078",
                  "label": "Fast Tempo"
                },
                {
                  "level": 2,
                  "descriptorID": "34293",
                  "label": "Very Fast"
                },
                {
                  "level": 3,
                  "descriptorID": "34347",
                  "label": "250s"
                }
              ]
            },
            "weight": "34"
          },
          {
            "ID": "34108",
            "genericName": "120's",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "98",
              "hierarchyRegionName": "TEMPO-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "34283",
                  "label": "Medium Tempo"
                },
                {
                  "level": 2,
                  "descriptorID": "34291",
                  "label": "Medium Fast"
                },
                {
                  "level": 3,
                  "descriptorID": "34325",
                  "label": "120s"
                }
              ]
            },
            "weight": "25"
          }
        ]
      }
    },
    {
      "objectType": "Track",
      "trackName": "For The Night (Featuring Lil Baby, DaBaby)",
      "album": {
        "albumName": "Hip Hop \u0026 Rap - Våren 2021",
        "releaseType": "Commercial - Multi Artist Collection"
      },
      "artist": {
        "artistName": "Various Artists"
      },
      "sonicDescriptors": {
        "moods": [
          {
            "ID": "90018",
            "genericName": "Edgy Slow Sensual Groove",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91144",
                  "label": "Sensual"
                },
                {
                  "level": 2,
                  "descriptorID": "91286",
                  "label": "Intimate"
                }
              ]
            },
            "weight": "35"
          },
          {
            "ID": "90019",
            "genericName": "Serious Upfront Expressive Sensual Beats",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91144",
                  "label": "Sensual"
                },
                {
                  "level": 2,
                  "descriptorID": "91286",
                  "label": "Intimate"
                }
              ]
            },
            "weight": "23"
          },
          {
            "ID": "34197",
            "genericName": "Dark Groovy / Savvy",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91308",
                  "label": "Dark Groovy"
                }
              ]
            },
            "weight": "18"
          },
          {
            "ID": "34193",
            "genericName": "Cool Confident Wary",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91311",
                  "label": "Wary / Defiant"
                }
              ]
            },
            "weight": "6"
          },
          {
            "ID": "90028",
            "genericName": "Hurt, Caring, Pride, Perseverance \u0026 Hope",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91295",
                  "label": "Cool Confidence"
                }
              ]
            },
            "weight": "5"
          },
          {
            "ID": "90041",
            "genericName": "Dark Strolling Edgy Cool Confessional",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91311",
                  "label": "Wary / Defiant"
                }
              ]
            },
            "weight": "4"
          },
          {
            "ID": "90020",
            "genericName": "Expressive Pulsing Desirous Groove",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91144",
                  "label": "Sensual"
                },
                {
                  "level": 2,
                  "descriptorID": "91286",
                  "label": "Intimate"
                }
              ]
            },
            "weight": "4"
          },
          {
            "ID": "90031",
            "genericName": "Sophisticated Cool Suave Empowered Groove",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91295",
                  "label": "Cool Confidence"
                }
              ]
            },
            "weight": "2"
          },
          {
            "ID": "90029",
            "genericName": "Kick-Back Dreamy Straightforward",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91295",
                  "label": "Cool Confidence"
                }
              ]
            },
            "weight": "2"
          },
          {
            "ID": "90038",
            "genericName": "Grim Unvarnished Truth",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91311",
                  "label": "Wary / Defiant"
                }
              ]
            },
            "weight": "2"
          }
        ],
        "styles": [
          {
            "ID": "84426",
            "genericName": "Mumble Rap",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89300",
                  "label": "Trap"
                }
              ]
            },
            "weight": "46"
          },
          {
            "ID": "88071",
            "genericName": "Trapsoul",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88905",
                  "label": "Soul/R\u0026B"
                },
                {
                  "level": 2,
                  "descriptorID": "89366",
                  "label": "Trapsoul"
                }
              ]
            },
            "weight": "21"
          },
          {
            "ID": "88072",
            "genericName": "Sad Trapsoul",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88905",
                  "label": "Soul/R\u0026B"
                },
                {
                  "level": 2,
                  "descriptorID": "89366",
                  "label": "Trapsoul"
                }
              ]
            },
            "weight": "14"
          },
          {
            "ID": "84278",
            "genericName": "Trap",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89300",
                  "label": "Trap"
                }
              ]
            },
            "weight": "6"
          },
          {
            "ID": "84424",
            "genericName": "Cloud Rap",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89300",
                  "label": "Trap"
                }
              ]
            },
            "weight": "6"
          },
          {
            "ID": "88067",
            "genericName": "Emo Rap",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89300",
                  "label": "Trap"
                }
              ]
            },
            "weight": "2"
          },
          {
            "ID": "84331",
            "genericName": "Urban Contemporary: R\u0026B",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88905",
                  "label": "Soul/R\u0026B"
                },
                {
                  "level": 2,
                  "descriptorID": "89364",
                  "label": "Contemporary R\u0026B"
                }
              ]
            },
            "weight": "1"
          },
          {
            "ID": "84282",
            "genericName": "Rap / R\u0026B Crossover",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89298",
                  "label": "Rap / R\u0026B Crossover"
                }
              ]
            },
            "weight": "1"
          }
        ],
        "tempos": [
          {
            "ID": "34094",
            "genericName": "60's",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "98",
              "hierarchyRegionName": "TEMPO-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "34283",
                  "label": "Medium Tempo"
                },
                {
                  "level": 2,
                  "descriptorID": "34290",
                  "label": "Medium"
                },
                {
                  "level": 3,
                  "descriptorID": "34311",
                  "label": "60s"
                }
              ]
            },
            "weight": "41"
          },
          {
            "ID": "34130",
            "genericName": "250's",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "98",
              "hierarchyRegionName": "TEMPO-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "43078",
                  "label": "Fast Tempo"
                },
                {
                  "level": 2,
                  "descriptorID": "34293",
                  "label": "Very Fast"
                },
                {
                  "level": 3,
                  "descriptorID": "34347",
                  "label": "250s"
                }
              ]
            },
            "weight": "35"
          },
          {
            "ID": "34108",
            "genericName": "120's",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "98",
              "hierarchyRegionName": "TEMPO-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "34283",
                  "label": "Medium Tempo"
                },
                {
                  "level": 2,
                  "descriptorID": "34291",
                  "label": "Medium Fast"
                },
                {
                  "level": 3,
                  "descriptorID": "34325",
                  "label": "120s"
                }
              ]
            },
            "weight": "24"
          }
        ]
      }
    },
    {
      "objectType": "Track",
      "trackName": "For The Night (Featuring Lil Baby, DaBaby)",
      "album": {
        "albumName": "Rap Everyone Knows",
        "releaseType": "Commercial - Multi Artist Collection"
      },
      "artist": {
        "artistName": "Various Artists"
      },
      "sonicDescriptors": {
        "moods": [
          {
            "ID": "90018",
            "genericName": "Edgy Slow Sensual Groove",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91144",
                  "label": "Sensual"
                },
                {
                  "level": 2,
                  "descriptorID": "91286",
                  "label": "Intimate"
                }
              ]
            },
            "weight": "29"
          },
          {
            "ID": "90019",
            "genericName": "Serious Upfront Expressive Sensual Beats",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91144",
                  "label": "Sensual"
                },
                {
                  "level": 2,
                  "descriptorID": "91286",
                  "label": "Intimate"
                }
              ]
            },
            "weight": "20"
          },
          {
            "ID": "34197",
            "genericName": "Dark Groovy / Savvy",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91308",
                  "label": "Dark Groovy"
                }
              ]
            },
            "weight": "18"
          },
          {
            "ID": "90028",
            "genericName": "Hurt, Caring, Pride, Perseverance \u0026 Hope",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91295",
                  "label": "Cool Confidence"
                }
              ]
            },
            "weight": "8"
          },
          {
            "ID": "34193",
            "genericName": "Cool Confident Wary",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91311",
                  "label": "Wary / Defiant"
                }
              ]
            },
            "weight": "7"
          },
          {
            "ID": "90041",
            "genericName": "Dark Strolling Edgy Cool Confessional",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91311",
                  "label": "Wary / Defiant"
                }
              ]
            },
            "weight": "6"
          },
          {
            "ID": "90020",
            "genericName": "Expressive Pulsing Desirous Groove",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91144",
                  "label": "Sensual"
                },
                {
                  "level": 2,
                  "descriptorID": "91286",
                  "label": "Intimate"
                }
              ]
            },
            "weight": "5"
          },
          {
            "ID": "90029",
            "genericName": "Kick-Back Dreamy Straightforward",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91295",
                  "label": "Cool Confidence"
                }
              ]
            },
            "weight": "2"
          },
          {
            "ID": "90209",
            "genericName": "Epic Dark Serious / Building Hope",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91158",
                  "label": "Empowering"
                },
                {
                  "level": 2,
                  "descriptorID": "91532",
                  "label": "Idealistic / Stirring"
                }
              ]
            },
            "weight": "2"
          },
          {
            "ID": "90038",
            "genericName": "Grim Unvarnished Truth",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91311",
                  "label": "Wary / Defiant"
                }
              ]
            },
            "weight": "2"
          }
        ],
        "styles": [
          {
            "ID": "84426",
            "genericName": "Mumble Rap",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89300",
                  "label": "Trap"
                }
              ]
            },
            "weight": "45"
          },
          {
            "ID": "88071",
            "genericName": "Trapsoul",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88905",
                  "label": "Soul/R\u0026B"
                },
                {
                  "level": 2,
                  "descriptorID": "89366",
                  "label": "Trapsoul"
                }
              ]
            },
            "weight": "22"
          },
          {
            "ID": "88072",
            "genericName": "Sad Trapsoul",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88905",
                  "label": "Soul/R\u0026B"
                },
                {
                  "level": 2,
                  "descriptorID": "89366",
                  "label": "Trapsoul"
                }
              ]
            },
            "weight": "15"
          },
          {
            "ID": "84278",
            "genericName": "Trap",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89300",
                  "label": "Trap"
                }
              ]
            },
            "weight": "6"
          },
          {
            "ID": "84424",
            "genericName": "Cloud Rap",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89300",
                  "label": "Trap"
                }
              ]
            },
            "weight": "6"
          },
          {
            "ID": "88067",
            "genericName": "Emo Rap",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89300",
                  "label": "Trap"
                }
              ]
            },
            "weight": "2"
          },
          {
            "ID": "84331",
            "genericName": "Urban Contemporary: R\u0026B",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88905",
                  "label": "Soul/R\u0026B"
                },
                {
                  "level": 2,
                  "descriptorID": "89364",
                  "label": "Contemporary R\u0026B"
                }
              ]
            },
            "weight": "1"
          },
          {
            "ID": "84282",
            "genericName": "Rap / R\u0026B Crossover",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89298",
                  "label": "Rap / R\u0026B Crossover"
                }
              ]
            },
            "weight": "1"
          }
        ],
        "tempos": [
          {
            "ID": "34094",
            "genericName": "60's",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "98",
              "hierarchyRegionName": "TEMPO-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "34283",
                  "label": "Medium Tempo"
                },
                {
                  "level": 2,
                  "descriptorID": "34290",
                  "label": "Medium"
                },
                {
                  "level": 3,
                  "descriptorID": "34311",
                  "label": "60s"
                }
              ]
            },
            "weight": "40"
          },
          {
            "ID": "34130",
            "genericName": "250's",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "98",
              "hierarchyRegionName": "TEMPO-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "43078",
                  "label": "Fast Tempo"
                },
                {
                  "level": 2,
                  "descriptorID": "34293",
                  "label": "Very Fast"
                },
                {
                  "level": 3,
                  "descriptorID": "34347",
                  "label": "250s"
                }
              ]
            },
            "weight": "34"
          },
          {
            "ID": "34108",
            "genericName": "120's",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "98",
              "hierarchyRegionName": "TEMPO-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "34283",
                  "label": "Medium Tempo"
                },
                {
                  "level": 2,
                  "descriptorID": "34291",
                  "label": "Medium Fast"
                },
                {
                  "level": 3,
                  "descriptorID": "34325",
                  "label": "120s"
                }
              ]
            },
            "weight": "25"
          }
        ]
      }
    },
    {
      "objectType": "Track",
      "trackName": "For The Night (Featuring Lil Baby, DaBaby)",
      "album": {
        "albumName": "Top Hits Vol 2",
        "releaseType": "Commercial - Multi Artist Collection"
      },
      "artist": {
        "artistName": "Various Artists"
      },
      "sonicDescriptors": {
        "moods": [
          {
            "ID": "90018",
            "genericName": "Edgy Slow Sensual Groove",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91144",
                  "label": "Sensual"
                },
                {
                  "level": 2,
                  "descriptorID": "91286",
                  "label": "Intimate"
                }
              ]
            },
            "weight": "30"
          },
          {
            "ID": "34197",
            "genericName": "Dark Groovy / Savvy",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91308",
                  "label": "Dark Groovy"
                }
              ]
            },
            "weight": "18"
          },
          {
            "ID": "90019",
            "genericName": "Serious Upfront Expressive Sensual Beats",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91144",
                  "label": "Sensual"
                },
                {
                  "level": 2,
                  "descriptorID": "91286",
                  "label": "Intimate"
                }
              ]
            },
            "weight": "18"
          },
          {
            "ID": "90028",
            "genericName": "Hurt, Caring, Pride, Perseverance \u0026 Hope",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91295",
                  "label": "Cool Confidence"
                }
              ]
            },
            "weight": "7"
          },
          {
            "ID": "34193",
            "genericName": "Cool Confident Wary",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91311",
                  "label": "Wary / Defiant"
                }
              ]
            },
            "weight": "7"
          },
          {
            "ID": "90041",
            "genericName": "Dark Strolling Edgy Cool Confessional",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91311",
                  "label": "Wary / Defiant"
                }
              ]
            },
            "weight": "6"
          },
          {
            "ID": "90020",
            "genericName": "Expressive Pulsing Desirous Groove",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91144",
                  "label": "Sensual"
                },
                {
                  "level": 2,
                  "descriptorID": "91286",
                  "label": "Intimate"
                }
              ]
            },
            "weight": "5"
          },
          {
            "ID": "90038",
            "genericName": "Grim Unvarnished Truth",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91311",
                  "label": "Wary / Defiant"
                }
              ]
            },
            "weight": "2"
          },
          {
            "ID": "90029",
            "genericName": "Kick-Back Dreamy Straightforward",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91295",
                  "label": "Cool Confidence"
                }
              ]
            },
            "weight": "2"
          },
          {
            "ID": "90209",
            "genericName": "Epic Dark Serious / Building Hope",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91158",
                  "label": "Empowering"
                },
                {
                  "level": 2,
                  "descriptorID": "91532",
                  "label": "Idealistic / Stirring"
                }
              ]
            },
            "weight": "2"
          }
        ],
        "styles": [
          {
            "ID": "84426",
            "genericName": "Mumble Rap",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89300",
                  "label": "Trap"
                }
              ]
            },
            "weight": "46"
          },
          {
            "ID": "88071",
            "genericName": "Trapsoul",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88905",
                  "label": "Soul/R\u0026B"
                },
                {
                  "level": 2,
                  "descriptorID": "89366",
                  "label": "Trapsoul"
                }
              ]
            },
            "weight": "21"
          },
          {
            "ID": "88072",
            "genericName": "Sad Trapsoul",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88905",
                  "label": "Soul/R\u0026B"
                },
                {
                  "level": 2,
                  "descriptorID": "89366",
                  "label": "Trapsoul"
                }
              ]
            },
            "weight": "13"
          },
          {
            "ID": "84278",
            "genericName": "Trap",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89300",
                  "label": "Trap"
                }
              ]
            },
            "weight": "7"
          },
          {
            "ID": "84424",
            "genericName": "Cloud Rap",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89300",
                  "label": "Trap"
                }
              ]
            },
            "weight": "6"
          },
          {
            "ID": "88067",
            "genericName": "Emo Rap",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89300",
                  "label": "Trap"
                }
              ]
            },
            "weight": "2"
          },
          {
            "ID": "84331",
            "genericName": "Urban Contemporary: R\u0026B",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88905",
                  "label": "Soul/R\u0026B"
                },
                {
                  "level": 2,
                  "descriptorID": "89364",
                  "label": "Contemporary R\u0026B"
                }
              ]
            },
            "weight": "1"
          },
          {
            "ID": "84282",
            "genericName": "Rap / R\u0026B Crossover",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89298",
                  "label": "Rap / R\u0026B Crossover"
                }
              ]
            },
            "weight": "1"
          }
        ],
        "tempos": [
          {
            "ID": "34094",
            "genericName": "60's",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "98",
              "hierarchyRegionName": "TEMPO-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "34283",
                  "label": "Medium Tempo"
                },
                {
                  "level": 2,
                  "descriptorID": "34290",
                  "label": "Medium"
                },
                {
                  "level": 3,
                  "descriptorID": "34311",
                  "label": "60s"
                }
              ]
            },
            "weight": "40"
          },
          {
            "ID": "34130",
            "genericName": "250's",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "98",
              "hierarchyRegionName": "TEMPO-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "43078",
                  "label": "Fast Tempo"
                },
                {
                  "level": 2,
                  "descriptorID": "34293",
                  "label": "Very Fast"
                },
                {
                  "level": 3,
                  "descriptorID": "34347",
                  "label": "250s"
                }
              ]
            },
            "weight": "34"
          },
          {
            "ID": "34108",
            "genericName": "120's",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "98",
              "hierarchyRegionName": "TEMPO-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "34283",
                  "label": "Medium Tempo"
                },
                {
                  "level": 2,
                  "descriptorID": "34291",
                  "label": "Medium Fast"
                },
                {
                  "level": 3,
                  "descriptorID": "34325",
                  "label": "120s"
                }
              ]
            },
            "weight": "25"
          }
        ]
      }
    },
    {
      "objectType": "Track",
      "trackName": "For The Night (Featuring Lil Baby, DaBaby)",
      "album": {
        "albumName": "New York Rap",
        "releaseType": "Commercial - Multi Artist Collection"
      },
      "artist": {
        "artistName": "Various Artists"
      },
      "sonicDescriptors": {
        "moods": [
          {
            "ID": "90018",
            "genericName": "Edgy Slow Sensual Groove",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91144",
                  "label": "Sensual"
                },
                {
                  "level": 2,
                  "descriptorID": "91286",
                  "label": "Intimate"
                }
              ]
            },
            "weight": "33"
          },
          {
            "ID": "90019",
            "genericName": "Serious Upfront Expressive Sensual Beats",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91144",
                  "label": "Sensual"
                },
                {
                  "level": 2,
                  "descriptorID": "91286",
                  "label": "Intimate"
                }
              ]
            },
            "weight": "21"
          },
          {
            "ID": "34197",
            "genericName": "Dark Groovy / Savvy",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91308",
                  "label": "Dark Groovy"
                }
              ]
            },
            "weight": "17"
          },
          {
            "ID": "34193",
            "genericName": "Cool Confident Wary",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91311",
                  "label": "Wary / Defiant"
                }
              ]
            },
            "weight": "7"
          },
          {
            "ID": "90041",
            "genericName": "Dark Strolling Edgy Cool Confessional",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91311",
                  "label": "Wary / Defiant"
                }
              ]
            },
            "weight": "6"
          },
          {
            "ID": "90028",
            "genericName": "Hurt, Caring, Pride, Perseverance \u0026 Hope",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91295",
                  "label": "Cool Confidence"
                }
              ]
            },
            "weight": "5"
          },
          {
            "ID": "90020",
            "genericName": "Expressive Pulsing Desirous Groove",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91144",
                  "label": "Sensual"
                },
                {
                  "level": 2,
                  "descriptorID": "91286",
                  "label": "Intimate"
                }
              ]
            },
            "weight": "4"
          },
          {
            "ID": "90038",
            "genericName": "Grim Unvarnished Truth",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91311",
                  "label": "Wary / Defiant"
                }
              ]
            },
            "weight": "2"
          },
          {
            "ID": "90031",
            "genericName": "Sophisticated Cool Suave Empowered Groove",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91295",
                  "label": "Cool Confidence"
                }
              ]
            },
            "weight": "2"
          },
          {
            "ID": "90029",
            "genericName": "Kick-Back Dreamy Straightforward",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91295",
                  "label": "Cool Confidence"
                }
              ]
            },
            "weight": "2"
          }
        ],
        "styles": [
          {
            "ID": "84426",
            "genericName": "Mumble Rap",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89300",
                  "label": "Trap"
                }
              ]
            },
            "weight": "43"
          },
          {
            "ID": "88071",
            "genericName": "Trapsoul",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88905",
                  "label": "Soul/R\u0026B"
                },
                {
                  "level": 2,
                  "descriptorID": "89366",
                  "label": "Trapsoul"
                }
              ]
            },
            "weight": "23"
          },
          {
            "ID": "88072",
            "genericName": "Sad Trapsoul",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88905",
                  "label": "Soul/R\u0026B"
                },
                {
                  "level": 2,
                  "descriptorID": "89366",
                  "label": "Trapsoul"
                }
              ]
            },
            "weight": "14"
          },
          {
            "ID": "84278",
            "genericName": "Trap",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89300",
                  "label": "Trap"
                }
              ]
            },
            "weight": "7"
          },
          {
            "ID": "84424",
            "genericName": "Cloud Rap",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89300",
                  "label": "Trap"
                }
              ]
            },
            "weight": "6"
          },
          {
            "ID": "88067",
            "genericName": "Emo Rap",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89300",
                  "label": "Trap"
                }
              ]
            },
            "weight": "2"
          },
          {
            "ID": "84331",
            "genericName": "Urban Contemporary: R\u0026B",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88905",
                  "label": "Soul/R\u0026B"
                },
                {
                  "level": 2,
                  "descriptorID": "89364",
                  "label": "Contemporary R\u0026B"
                }
              ]
            },
            "weight": "1"
          },
          {
            "ID": "84282",
            "genericName": "Rap / R\u0026B Crossover",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89298",
                  "label": "Rap / R\u0026B Crossover"
                }
              ]
            },
            "weight": "1"
          }
        ],
        "tempos": [
          {
            "ID": "34094",
            "genericName": "60's",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "98",
              "hierarchyRegionName": "TEMPO-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "34283",
                  "label": "Medium Tempo"
                },
                {
                  "level": 2,
                  "descriptorID": "34290",
                  "label": "Medium"
                },
                {
                  "level": 3,
                  "descriptorID": "34311",
                  "label": "60s"
                }
              ]
            },
            "weight": "40"
          },
          {
            "ID": "34130",
            "genericName": "250's",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "98",
              "hierarchyRegionName": "TEMPO-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "43078",
                  "label": "Fast Tempo"
                },
                {
                  "level": 2,
                  "descriptorID": "34293",
                  "label": "Very Fast"
                },
                {
                  "level": 3,
                  "descriptorID": "34347",
                  "label": "250s"
                }
              ]
            },
            "weight": "34"
          },
          {
            "ID": "34108",
            "genericName": "120's",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "98",
              "hierarchyRegionName": "TEMPO-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "34283",
                  "label": "Medium Tempo"
                },
                {
                  "level": 2,
                  "descriptorID": "34291",
                  "label": "Medium Fast"
                },
                {
                  "level": 3,
                  "descriptorID": "34325",
                  "label": "120s"
                }
              ]
            },
            "weight": "25"
          }
        ]
      }
    },
    {
      "objectType": "Track",
      "trackName": "For The Night (Featuring Lil Baby, DaBaby)",
      "album": {
        "albumName": "New York Rap",
        "releaseType": "Commercial - Multi Artist Collection"
      },
      "artist": {
        "artistName": "Various Artists"
      },
      "sonicDescriptors": {
        "moods": [
          {
            "ID": "90018",
            "genericName": "Edgy Slow Sensual Groove",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91144",
                  "label": "Sensual"
                },
                {
                  "level": 2,
                  "descriptorID": "91286",
                  "label": "Intimate"
                }
              ]
            },
            "weight": "33"
          },
          {
            "ID": "90019",
            "genericName": "Serious Upfront Expressive Sensual Beats",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91144",
                  "label": "Sensual"
                },
                {
                  "level": 2,
                  "descriptorID": "91286",
                  "label": "Intimate"
                }
              ]
            },
            "weight": "22"
          },
          {
            "ID": "34197",
            "genericName": "Dark Groovy / Savvy",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91308",
                  "label": "Dark Groovy"
                }
              ]
            },
            "weight": "18"
          },
          {
            "ID": "34193",
            "genericName": "Cool Confident Wary",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91311",
                  "label": "Wary / Defiant"
                }
              ]
            },
            "weight": "6"
          },
          {
            "ID": "90020",
            "genericName": "Expressive Pulsing Desirous Groove",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91144",
                  "label": "Sensual"
                },
                {
                  "level": 2,
                  "descriptorID": "91286",
                  "label": "Intimate"
                }
              ]
            },
            "weight": "5"
          },
          {
            "ID": "90028",
            "genericName": "Hurt, Caring, Pride, Perseverance \u0026 Hope",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91295",
                  "label": "Cool Confidence"
                }
              ]
            },
            "weight": "5"
          },
          {
            "ID": "90041",
            "genericName": "Dark Strolling Edgy Cool Confessional",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91311",
                  "label": "Wary / Defiant"
                }
              ]
            },
            "weight": "5"
          },
          {
            "ID": "90031",
            "genericName": "Sophisticated Cool Suave Empowered Groove",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91295",
                  "label": "Cool Confidence"
                }
              ]
            },
            "weight": "2"
          },
          {
            "ID": "90029",
            "genericName": "Kick-Back Dreamy Straightforward",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91295",
                  "label": "Cool Confidence"
                }
              ]
            },
            "weight": "2"
          },
          {
            "ID": "90038",
            "genericName": "Grim Unvarnished Truth",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91311",
                  "label": "Wary / Defiant"
                }
              ]
            },
            "weight": "2"
          }
        ],
        "styles": [
          {
            "ID": "84426",
            "genericName": "Mumble Rap",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89300",
                  "label": "Trap"
                }
              ]
            },
            "weight": "45"
          },
          {
            "ID": "88071",
            "genericName": "Trapsoul",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88905",
                  "label": "Soul/R\u0026B"
                },
                {
                  "level": 2,
                  "descriptorID": "89366",
                  "label": "Trapsoul"
                }
              ]
            },
            "weight": "22"
          },
          {
            "ID": "88072",
            "genericName": "Sad Trapsoul",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88905",
                  "label": "Soul/R\u0026B"
                },
                {
                  "level": 2,
                  "descriptorID": "89366",
                  "label": "Trapsoul"
                }
              ]
            },
            "weight": "14"
          },
          {
            "ID": "84278",
            "genericName": "Trap",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89300",
                  "label": "Trap"
                }
              ]
            },
            "weight": "6"
          },
          {
            "ID": "84424",
            "genericName": "Cloud Rap",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89300",
                  "label": "Trap"
                }
              ]
            },
            "weight": "6"
          },
          {
            "ID": "88067",
            "genericName": "Emo Rap",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89300",
                  "label": "Trap"
                }
              ]
            },
            "weight": "2"
          },
          {
            "ID": "84331",
            "genericName": "Urban Contemporary: R\u0026B",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88905",
                  "label": "Soul/R\u0026B"
                },
                {
                  "level": 2,
                  "descriptorID": "89364",
                  "label": "Contemporary R\u0026B"
                }
              ]
            },
            "weight": "1"
          },
          {
            "ID": "84282",
            "genericName": "Rap / R\u0026B Crossover",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89298",
                  "label": "Rap / R\u0026B Crossover"
                }
              ]
            },
            "weight": "1"
          }
        ],
        "tempos": [
          {
            "ID": "34094",
            "genericName": "60's",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "98",
              "hierarchyRegionName": "TEMPO-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "34283",
                  "label": "Medium Tempo"
                },
                {
                  "level": 2,
                  "descriptorID": "34290",
                  "label": "Medium"
                },
                {
                  "level": 3,
                  "descriptorID": "34311",
                  "label": "60s"
                }
              ]
            },
            "weight": "40"
          },
          {
            "ID": "34130",
            "genericName": "250's",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "98",
              "hierarchyRegionName": "TEMPO-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "43078",
                  "label": "Fast Tempo"
                },
                {
                  "level": 2,
                  "descriptorID": "34293",
                  "label": "Very Fast"
                },
                {
                  "level": 3,
                  "descriptorID": "34347",
                  "label": "250s"
                }
              ]
            },
            "weight": "34"
          },
          {
            "ID": "34108",
            "genericName": "120's",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "98",
              "hierarchyRegionName": "TEMPO-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "34283",
                  "label": "Medium Tempo"
                },
                {
                  "level": 2,
                  "descriptorID": "34291",
                  "label": "Medium Fast"
                },
                {
                  "level": 3,
                  "descriptorID": "34325",
                  "label": "120s"
                }
              ]
            },
            "weight": "25"
          }
        ]
      }
    },
    {
      "objectType": "Track",
      "trackName": "For The Night (Featuring Lil Baby, DaBaby)",
      "album": {
        "albumName": "Pop Deluxe",
        "releaseType": "Commercial - Multi Artist Collection"
      },
      "artist": {
        "artistName": "Various Artists"
      },
      "sonicDescriptors": {
        "moods": [
          {
            "ID": "90018",
            "genericName": "Edgy Slow Sensual Groove",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91144",
                  "label": "Sensual"
                },
                {
                  "level": 2,
                  "descriptorID": "91286",
                  "label": "Intimate"
                }
              ]
            },
            "weight": "33"
          },
          {
            "ID": "90019",
            "genericName": "Serious Upfront Expressive Sensual Beats",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91144",
                  "label": "Sensual"
                },
                {
                  "level": 2,
                  "descriptorID": "91286",
                  "label": "Intimate"
                }
              ]
            },
            "weight": "20"
          },
          {
            "ID": "34197",
            "genericName": "Dark Groovy / Savvy",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91308",
                  "label": "Dark Groovy"
                }
              ]
            },
            "weight": "17"
          },
          {
            "ID": "34193",
            "genericName": "Cool Confident Wary",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91311",
                  "label": "Wary / Defiant"
                }
              ]
            },
            "weight": "7"
          },
          {
            "ID": "90041",
            "genericName": "Dark Strolling Edgy Cool Confessional",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91311",
                  "label": "Wary / Defiant"
                }
              ]
            },
            "weight": "6"
          },
          {
            "ID": "90028",
            "genericName": "Hurt, Caring, Pride, Perseverance \u0026 Hope",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91295",
                  "label": "Cool Confidence"
                }
              ]
            },
            "weight": "6"
          },
          {
            "ID": "90020",
            "genericName": "Expressive Pulsing Desirous Groove",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91144",
                  "label": "Sensual"
                },
                {
                  "level": 2,
                  "descriptorID": "91286",
                  "label": "Intimate"
                }
              ]
            },
            "weight": "4"
          },
          {
            "ID": "90031",
            "genericName": "Sophisticated Cool Suave Empowered Groove",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91295",
                  "label": "Cool Confidence"
                }
              ]
            },
            "weight": "2"
          },
          {
            "ID": "90038",
            "genericName": "Grim Unvarnished Truth",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91311",
                  "label": "Wary / Defiant"
                }
              ]
            },
            "weight": "2"
          },
          {
            "ID": "90029",
            "genericName": "Kick-Back Dreamy Straightforward",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "176",
              "hierarchyRegionName": "MOODS-GN-DEFAULT2",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "91145",
                  "label": "Cool"
                },
                {
                  "level": 2,
                  "descriptorID": "91295",
                  "label": "Cool Confidence"
                }
              ]
            },
            "weight": "2"
          }
        ],
        "styles": [
          {
            "ID": "84426",
            "genericName": "Mumble Rap",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89300",
                  "label": "Trap"
                }
              ]
            },
            "weight": "44"
          },
          {
            "ID": "88071",
            "genericName": "Trapsoul",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88905",
                  "label": "Soul/R\u0026B"
                },
                {
                  "level": 2,
                  "descriptorID": "89366",
                  "label": "Trapsoul"
                }
              ]
            },
            "weight": "22"
          },
          {
            "ID": "88072",
            "genericName": "Sad Trapsoul",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88905",
                  "label": "Soul/R\u0026B"
                },
                {
                  "level": 2,
                  "descriptorID": "89366",
                  "label": "Trapsoul"
                }
              ]
            },
            "weight": "14"
          },
          {
            "ID": "84278",
            "genericName": "Trap",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89300",
                  "label": "Trap"
                }
              ]
            },
            "weight": "7"
          },
          {
            "ID": "84424",
            "genericName": "Cloud Rap",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89300",
                  "label": "Trap"
                }
              ]
            },
            "weight": "6"
          },
          {
            "ID": "88067",
            "genericName": "Emo Rap",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89300",
                  "label": "Trap"
                }
              ]
            },
            "weight": "2"
          },
          {
            "ID": "84331",
            "genericName": "Urban Contemporary: R\u0026B",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88905",
                  "label": "Soul/R\u0026B"
                },
                {
                  "level": 2,
                  "descriptorID": "89364",
                  "label": "Contemporary R\u0026B"
                }
              ]
            },
            "weight": "1"
          },
          {
            "ID": "84282",
            "genericName": "Rap / R\u0026B Crossover",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "160",
              "hierarchyRegionName": "SONIC-STYLES-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "88902",
                  "label": "Rap/Hip-Hop"
                },
                {
                  "level": 2,
                  "descriptorID": "89298",
                  "label": "Rap / R\u0026B Crossover"
                }
              ]
            },
            "weight": "1"
          }
        ],
        "tempos": [
          {
            "ID": "34094",
            "genericName": "60's",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "98",
              "hierarchyRegionName": "TEMPO-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "34283",
                  "label": "Medium Tempo"
                },
                {
                  "level": 2,
                  "descriptorID": "34290",
                  "label": "Medium"
                },
                {
                  "level": 3,
                  "descriptorID": "34311",
                  "label": "60s"
                }
              ]
            },
            "weight": "41"
          },
          {
            "ID": "34130",
            "genericName": "250's",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "98",
              "hierarchyRegionName": "TEMPO-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "43078",
                  "label": "Fast Tempo"
                },
                {
                  "level": 2,
                  "descriptorID": "34293",
                  "label": "Very Fast"
                },
                {
                  "level": 3,
                  "descriptorID": "34347",
                  "label": "250s"
                }
              ]
            },
            "weight": "35"
          },
          {
            "ID": "34108",
            "genericName": "120's",
            "localizedLabels": {
              "languageCode": "en",
              "language": "English",
              "hierarchyRegionID": "98",
              "hierarchyRegionName": "TEMPO-DEFAULT",
              "localizedNames": [
                {
                  "level": 1,
                  "descriptorID": "34283",
                  "label": "Medium Tempo"
                },
                {
                  "level": 2,
                  "descriptorID": "34291",
                  "label": "Medium Fast"
                },
                {
                  "level": 3,
                  "descriptorID": "34325",
                  "label": "120s"
                }
              ]
            },
            "weight": "24"
          }
        ]
      }
    }
  ]
}
```