# sonic-descriptor-api

## Summary
The Sonic Descriptor API is an endpoint of Gracenote’s GMD API, which allows customers to look up Recording-level Sonic descriptors such as Mood, Style, and Tempo (where available) given an ISRC. We suggest that customers use this endpoint to retrieve descriptors for New Releases which may not yet be available in either of the GMD API’s Recording endpoints, but revert back to the Recording endpoints once the track has been normalized into a Recording.
Note that returned objects are based on what packages and add ons a customer is licensed to receive.


## Prerequisites
A GMD API key is required to access the Sonic Descriptor API. For more information, please contact your Gracenote representative.

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

## Response

### Response fields
| Field | Description |
|-|-|
| Meta | the meta field showing the track objects total number, count and offset |
| Data | the data field for detailed track objects |

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

## Example 1

### request
```
curl "https://api.gmd.music.gracenote.com/v1.1/tracks/isrc?id=USUM72013355&apikey={apikey}"
```

### response
```
{
  "meta": {
    "total": 10,
    "count": 10,
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
          {...}
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
          {...}
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
          {...}
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
          {...}
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
          {...}
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
          {...}
        ]
      }
    },
    {...},
    {...},
    {...},
    {...},
    {...},
    {...},
    {...},
    {...}
  ]
}
```

## Example 2

### request
```
curl "https://api.gmd.music.gracenote.com/v1.1/tracks/isrc?id=USUM72013355&limit=2&offset=5&apikey={apikey}"
```

### response
```
{
  "meta": {
    "total": 10,
    "count": 2,
    "offset": 5
  },
  "data": [
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
          {...},
          {...},
          {...},
          {...},
          {...},
          {...},
          {...},
          {...}
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
          {...},
          {...},
          {...},
          {...},
          {...},
          {...},
          {...}
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
          {...}
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
          {...},
          {...},
          {...},
          {...},
          {...},
          {...},
          {...},
          {...}
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
          {...},
          {...},
          {...},
          {...},
          {...},
          {...},
          {...}
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
          {...}
        ]
      }
    }
  ]
}
```
