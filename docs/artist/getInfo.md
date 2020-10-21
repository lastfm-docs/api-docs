Get the metadata and tracklist for an album on Last.fm using the album name or a musicbrainz id.

No authentication required.

## Parameters

| Method        | Type                                                                                              | Default | Required                      | Description                                                                                                           |
| ------------- | ------------------------------------------------------------------------------------------------- | ------- | ----------------------------- | --------------------------------------------------------------------------------------------------------------------- |
| `artist`      | [string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) | `none`  | Yes (unless mbid)        | The artist name to fetch information for.                                                                             |
| `mbid`        | [string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) | `none`  | Yes (unless artist name) | MusicBrainz ID as an alternative for the artist's name.                                                               |
| `autocorrect` | [number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) | 0       |  | Transform misspelled artist names into correct artist names, returning the correct version instead. The corrected artist name will be returned in the response.                                                             |
| `username`    | [string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) | `none`  |  | The username for the context of the request. If supplied, the user's playcount for this artist is included in the response. |
| `lang`        | [string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) | en      |  | The language to return the biography in, expressed as an ISO 639 alpha-2 code.                      |
| `api_key`     | [token](https://www.last.fm/api/account/create)                                                   | `none`  | Yes            | A Last.fm API key.                                                                                                    |

## Responses

Errors:

- 2 : Invalid service - This service does not exist
- 3 : Invalid Method - No method with that name in this package
- 4 : Authentication Failed - You do not have permissions to access the service
- 5 : Invalid format - This service doesn't exist in that format
- 6 : Invalid parameters - Your request is missing a required parameter
- 7 : Invalid resource specified
- 8 : Operation failed - Something else went wrong
- 9 : Invalid session key - Please re-authenticate
- 10 : Invalid API key - You must be granted a valid key by last.fm
- 11 : Service Offline - This service is temporarily offline. Try again later.
- 13 : Invalid method signature supplied
- 16 : There was a temporary error processing your request. Please try again
- 26 : Suspended API key - Access for your account has been suspended, please contact Last.fm
- 29 : Rate limit exceeded - Your IP has made too many requests in a short period

## Examples

??? note "Example response with user parameter"

    | Parameter | Value         |
    | --------- | ------------- |
    | artist    | The Weeknd    |
    | api_key   | YOUR_API_KEY  |
    | username  | TyphoonsNotABot |
    | format    | json          |

    HTTP status: `200 OK`

    ```
    https://ws.audioscrobbler.com/2.0/?method=artist.getinfo&artist=The+Weeknd&username=TyphoonsNotABot&api_key=YOUR_API_KEY&format=json
    ```
    ```json
        {
      "artist": {
        "name": "The Weeknd",
        "mbid": "c8b03190-306c-4120-bb0b-6f2ebfc06ea9",
        "url": "https://www.last.fm/music/The+Weeknd",
        "image": [
          {
            "#text": "https://lastfm.freetls.fastly.net/i/u/34s/2a96cbd8b46e442fc41c2b86b821562f.png",
            "size": "small"
          },
          {
            "#text": "https://lastfm.freetls.fastly.net/i/u/64s/2a96cbd8b46e442fc41c2b86b821562f.png",
            "size": "medium"
          },
          {
            "#text": "https://lastfm.freetls.fastly.net/i/u/174s/2a96cbd8b46e442fc41c2b86b821562f.png",
            "size": "large"
          },
          {
            "#text": "https://lastfm.freetls.fastly.net/i/u/300x300/2a96cbd8b46e442fc41c2b86b821562f.png",
            "size": "extralarge"
          },
          {
            "#text": "https://lastfm.freetls.fastly.net/i/u/300x300/2a96cbd8b46e442fc41c2b86b821562f.png",
            "size": "mega"
          },
          {
            "#text": "https://lastfm.freetls.fastly.net/i/u/300x300/2a96cbd8b46e442fc41c2b86b821562f.png",
            "size": ""
          }
        ],
        "streamable": "0",
        "ontour": "0",
        "stats": {
          "listeners": "1688480",
          "playcount": "135692303",
          "userplaycount": "7211"
        },
        "similar": {
          "artist": [
            {
              "name": "Drake",
              "url": "https://www.last.fm/music/Drake",
              "image": [
                {
                  "#text": "https://lastfm.freetls.fastly.net/i/u/34s/2a96cbd8b46e442fc41c2b86b821562f.png",
                  "size": "small"
                },
                {
                  "#text": "https://lastfm.freetls.fastly.net/i/u/64s/2a96cbd8b46e442fc41c2b86b821562f.png",
                  "size": "medium"
                },
                {
                  "#text": "https://lastfm.freetls.fastly.net/i/u/174s/2a96cbd8b46e442fc41c2b86b821562f.png",
                  "size": "large"
                },
                {
                  "#text": "https://lastfm.freetls.fastly.net/i/u/300x300/2a96cbd8b46e442fc41c2b86b821562f.png",
                  "size": "extralarge"
                },
                {
                  "#text": "https://lastfm.freetls.fastly.net/i/u/300x300/2a96cbd8b46e442fc41c2b86b821562f.png",
                  "size": "mega"
                },
                {
                  "#text": "https://lastfm.freetls.fastly.net/i/u/300x300/2a96cbd8b46e442fc41c2b86b821562f.png",
                  "size": ""
                }
              ]
            },
            {
              "name": "PARTYNEXTDOOR",
              "url": "https://www.last.fm/music/PARTYNEXTDOOR",
              "image": [
                {
                  "#text": "https://lastfm.freetls.fastly.net/i/u/34s/2a96cbd8b46e442fc41c2b86b821562f.png",
                  "size": "small"
                },
                {
                  "#text": "https://lastfm.freetls.fastly.net/i/u/64s/2a96cbd8b46e442fc41c2b86b821562f.png",
                  "size": "medium"
                },
                {
                  "#text": "https://lastfm.freetls.fastly.net/i/u/174s/2a96cbd8b46e442fc41c2b86b821562f.png",
                  "size": "large"
                },
                {
                  "#text": "https://lastfm.freetls.fastly.net/i/u/300x300/2a96cbd8b46e442fc41c2b86b821562f.png",
                  "size": "extralarge"
                },
                {
                  "#text": "https://lastfm.freetls.fastly.net/i/u/300x300/2a96cbd8b46e442fc41c2b86b821562f.png",
                  "size": "mega"
                },
                {
                  "#text": "https://lastfm.freetls.fastly.net/i/u/300x300/2a96cbd8b46e442fc41c2b86b821562f.png",
                  "size": ""
                }
              ]
            },
            {
              "name": "Bryson Tiller",
              "url": "https://www.last.fm/music/Bryson+Tiller",
              "image": [
                {
                  "#text": "https://lastfm.freetls.fastly.net/i/u/34s/2a96cbd8b46e442fc41c2b86b821562f.png",
                  "size": "small"
                },
                {
                  "#text": "https://lastfm.freetls.fastly.net/i/u/64s/2a96cbd8b46e442fc41c2b86b821562f.png",
                  "size": "medium"
                },
                {
                  "#text": "https://lastfm.freetls.fastly.net/i/u/174s/2a96cbd8b46e442fc41c2b86b821562f.png",
                  "size": "large"
                },
                {
                  "#text": "https://lastfm.freetls.fastly.net/i/u/300x300/2a96cbd8b46e442fc41c2b86b821562f.png",
                  "size": "extralarge"
                },
                {
                  "#text": "https://lastfm.freetls.fastly.net/i/u/300x300/2a96cbd8b46e442fc41c2b86b821562f.png",
                  "size": "mega"
                },
                {
                  "#text": "https://lastfm.freetls.fastly.net/i/u/300x300/2a96cbd8b46e442fc41c2b86b821562f.png",
                  "size": ""
                }
              ]
            },
            {
              "name": "Frank Ocean",
              "url": "https://www.last.fm/music/Frank+Ocean",
              "image": [
                {
                  "#text": "https://lastfm.freetls.fastly.net/i/u/34s/2a96cbd8b46e442fc41c2b86b821562f.png",
                  "size": "small"
                },
                {
                  "#text": "https://lastfm.freetls.fastly.net/i/u/64s/2a96cbd8b46e442fc41c2b86b821562f.png",
                  "size": "medium"
                },
                {
                  "#text": "https://lastfm.freetls.fastly.net/i/u/174s/2a96cbd8b46e442fc41c2b86b821562f.png",
                  "size": "large"
                },
                {
                  "#text": "https://lastfm.freetls.fastly.net/i/u/300x300/2a96cbd8b46e442fc41c2b86b821562f.png",
                  "size": "extralarge"
                },
                {
                  "#text": "https://lastfm.freetls.fastly.net/i/u/300x300/2a96cbd8b46e442fc41c2b86b821562f.png",
                  "size": "mega"
                },
                {
                  "#text": "https://lastfm.freetls.fastly.net/i/u/300x300/2a96cbd8b46e442fc41c2b86b821562f.png",
                  "size": ""
                }
              ]
            },
            {
              "name": "Majid Jordan",
              "url": "https://www.last.fm/music/Majid+Jordan",
              "image": [
                {
                  "#text": "https://lastfm.freetls.fastly.net/i/u/34s/2a96cbd8b46e442fc41c2b86b821562f.png",
                  "size": "small"
                },
                {
                  "#text": "https://lastfm.freetls.fastly.net/i/u/64s/2a96cbd8b46e442fc41c2b86b821562f.png",
                  "size": "medium"
                },
                {
                  "#text": "https://lastfm.freetls.fastly.net/i/u/174s/2a96cbd8b46e442fc41c2b86b821562f.png",
                  "size": "large"
                },
                {
                  "#text": "https://lastfm.freetls.fastly.net/i/u/300x300/2a96cbd8b46e442fc41c2b86b821562f.png",
                  "size": "extralarge"
                },
                {
                  "#text": "https://lastfm.freetls.fastly.net/i/u/300x300/2a96cbd8b46e442fc41c2b86b821562f.png",
                  "size": "mega"
                },
                {
                  "#text": "https://lastfm.freetls.fastly.net/i/u/300x300/2a96cbd8b46e442fc41c2b86b821562f.png",
                  "size": ""
                }
              ]
            }
          ]
        },
        "tags": {
          "tag": [
            {
              "name": "rnb",
              "url": "https://www.last.fm/tag/rnb"
            },
            {
              "name": "electronic",
              "url": "https://www.last.fm/tag/electronic"
            },
            {
              "name": "dubstep",
              "url": "https://www.last.fm/tag/dubstep"
            },
            {
              "name": "Canadian",
              "url": "https://www.last.fm/tag/Canadian"
            },
            {
              "name": "prog-rnb",
              "url": "https://www.last.fm/tag/prog-rnb"
            }
          ]
        },
        "bio": {
          "links": {
            "link": {
              "#text": "",
              "rel": "original",
              "href": "https://last.fm/music/The+Weeknd/+wiki"
            }
          },
          "published": "09 Jan 2011, 12:41",
          "summary": "Abel Makkonen Tesfaye (born February 16, 1990 in Scarborough, Ontario), popularly known as The Weeknd, is an R&B/pop/hip-hop singer from Toronto, Canada. He has been referred to as the songbird of his generation and the best musical talent since Michael Jackson throughout his career.\n\nThe Weeknd gained widespread critical acclaim for his three mixtapes, House of Balloons, Thursday, and Echoes of Silence, which he later compiled to make a remastered, three-disc album titled Trilogy after signing his record deal with Republic. <a href=\"https://www.last.fm/music/The+Weeknd\">Read more on Last.fm</a>",
          "content": "Abel Makkonen Tesfaye (born February 16, 1990 in Scarborough, Ontario), popularly known as The Weeknd, is an R&B/pop/hip-hop singer from Toronto, Canada. He has been referred to as the songbird of his generation and the best musical talent since Michael Jackson throughout his career.\n\nThe Weeknd gained widespread critical acclaim for his three mixtapes, House of Balloons, Thursday, and Echoes of Silence, which he later compiled to make a remastered, three-disc album titled Trilogy after signing his record deal with Republic. In 2013, he released Kiss Land, which was considered to be his debut studio album.\n\nIn 2014, he dropped “Often,” a remix of Beyonce’s “Drunk In Love,” and “King of the Fall.” The Weeknd released two songs in collaboration with the film Fifty Shades of Grey, with “Earned It” becoming his solo breakout hit.\n\nHis second studio album became highly-anticipated, with riveting singles like “The Hills” and “Can’t Feel My Face” leaving fans hungry for more. Beauty Behind the Madness was released on August 28, 2015.\n\nHis third studio album, Starboy, was released on November 25, 2016. The Daft Punk-assisted title track led the project as its first official single, released on Wednesday, September 21, 2016, before becoming his third number one track in the United States, as also his home country, Canada.\nThe effort was a commercial success, topping the Billboard 200 albums chart with over 348,000 copies sold in its first week, all eighteen tracks debuting on the Billboard Hot 100, receiving a GRAMMY Award for the Best Urban Contemporary Album category at the 60th annual ceremony, overall for the second time in his music career and being ranked as the third most popular album of 2017 in the U.S.\n\nHis debut EP, My Dear Melancholy,, released on March 30, 2018 includes themes revolving around his breakups with Bella Hadid during summer of 2016 and Selena Gomez in October 2017, respectively. With the lead single, “Call Out My Name”, the Canadian singer earned the largest first-day Spotify stream count of any song released in 2018 at that time and his eighth Top 10 entry on Hot 100.\n\nTesfaye’s fourth studio album (and his first in three years), After Hours was officially released on March 20, 2020, and is named after a 1985 movie directed by his idol, Martin Scorsese. It was primarily supported by November 2019-released singles “Heartless” and “Blinding Lights,” with the pair becoming his fourth and fifth #1 singles in the US and the latter his first #1 single in the UK. The successful promotional title track and “In Your Eyes” were also released as singles. <a href=\"https://www.last.fm/music/The+Weeknd\">Read more on Last.fm</a>. User-contributed text is available under the Creative Commons By-SA License; additional terms may apply."
        }
      }
    }
    ```
    
??? note "Example response without user parameter"

    | Parameter | Value         |
    | --------- | ------------- |
    | artist    | The Weeknd    |
    | api_key   | YOUR_API_KEY  |
    | format    | json          |

    HTTP status: `200 OK`

    ```
    https://ws.audioscrobbler.com/2.0/?method=artist.getinfo&artist=The+Weeknd&username=TyphoonsNotABot&api_key=YOUR_API_KEY&format=json
    ```
    
    ```json
          {
        "artist": {
          "name": "The Weeknd",
          "mbid": "c8b03190-306c-4120-bb0b-6f2ebfc06ea9",
          "url": "https://www.last.fm/music/The+Weeknd",
          "image": [
            {
              "#text": "https://lastfm.freetls.fastly.net/i/u/34s/2a96cbd8b46e442fc41c2b86b821562f.png",
              "size": "small"
            },
            {
              "#text": "https://lastfm.freetls.fastly.net/i/u/64s/2a96cbd8b46e442fc41c2b86b821562f.png",
              "size": "medium"
            },
            {
              "#text": "https://lastfm.freetls.fastly.net/i/u/174s/2a96cbd8b46e442fc41c2b86b821562f.png",
              "size": "large"
            },
            {
              "#text": "https://lastfm.freetls.fastly.net/i/u/300x300/2a96cbd8b46e442fc41c2b86b821562f.png",
              "size": "extralarge"
            },
            {
              "#text": "https://lastfm.freetls.fastly.net/i/u/300x300/2a96cbd8b46e442fc41c2b86b821562f.png",
              "size": "mega"
            },
            {
              "#text": "https://lastfm.freetls.fastly.net/i/u/300x300/2a96cbd8b46e442fc41c2b86b821562f.png",
              "size": ""
            }
          ],
          "streamable": "0",
          "ontour": "0",
          "stats": {
            "listeners": "1688480",
            "playcount": "135692303"
          },
          "similar": {
            "artist": [
              {
                "name": "Drake",
                "url": "https://www.last.fm/music/Drake",
                "image": [
                  {
                    "#text": "https://lastfm.freetls.fastly.net/i/u/34s/2a96cbd8b46e442fc41c2b86b821562f.png",
                    "size": "small"
                  },
                  {
                    "#text": "https://lastfm.freetls.fastly.net/i/u/64s/2a96cbd8b46e442fc41c2b86b821562f.png",
                    "size": "medium"
                  },
                  {
                    "#text": "https://lastfm.freetls.fastly.net/i/u/174s/2a96cbd8b46e442fc41c2b86b821562f.png",
                    "size": "large"
                  },
                  {
                    "#text": "https://lastfm.freetls.fastly.net/i/u/300x300/2a96cbd8b46e442fc41c2b86b821562f.png",
                    "size": "extralarge"
                  },
                  {
                    "#text": "https://lastfm.freetls.fastly.net/i/u/300x300/2a96cbd8b46e442fc41c2b86b821562f.png",
                    "size": "mega"
                  },
                  {
                    "#text": "https://lastfm.freetls.fastly.net/i/u/300x300/2a96cbd8b46e442fc41c2b86b821562f.png",
                    "size": ""
                  }
                ]
              },
              {
                "name": "PARTYNEXTDOOR",
                "url": "https://www.last.fm/music/PARTYNEXTDOOR",
                "image": [
                  {
                    "#text": "https://lastfm.freetls.fastly.net/i/u/34s/2a96cbd8b46e442fc41c2b86b821562f.png",
                    "size": "small"
                  },
                  {
                    "#text": "https://lastfm.freetls.fastly.net/i/u/64s/2a96cbd8b46e442fc41c2b86b821562f.png",
                    "size": "medium"
                  },
                  {
                    "#text": "https://lastfm.freetls.fastly.net/i/u/174s/2a96cbd8b46e442fc41c2b86b821562f.png",
                    "size": "large"
                  },
                  {
                    "#text": "https://lastfm.freetls.fastly.net/i/u/300x300/2a96cbd8b46e442fc41c2b86b821562f.png",
                    "size": "extralarge"
                  },
                  {
                    "#text": "https://lastfm.freetls.fastly.net/i/u/300x300/2a96cbd8b46e442fc41c2b86b821562f.png",
                    "size": "mega"
                  },
                  {
                    "#text": "https://lastfm.freetls.fastly.net/i/u/300x300/2a96cbd8b46e442fc41c2b86b821562f.png",
                    "size": ""
                  }
                ]
              },
              {
                "name": "Bryson Tiller",
                "url": "https://www.last.fm/music/Bryson+Tiller",
                "image": [
                  {
                    "#text": "https://lastfm.freetls.fastly.net/i/u/34s/2a96cbd8b46e442fc41c2b86b821562f.png",
                    "size": "small"
                  },
                  {
                    "#text": "https://lastfm.freetls.fastly.net/i/u/64s/2a96cbd8b46e442fc41c2b86b821562f.png",
                    "size": "medium"
                  },
                  {
                    "#text": "https://lastfm.freetls.fastly.net/i/u/174s/2a96cbd8b46e442fc41c2b86b821562f.png",
                    "size": "large"
                  },
                  {
                    "#text": "https://lastfm.freetls.fastly.net/i/u/300x300/2a96cbd8b46e442fc41c2b86b821562f.png",
                    "size": "extralarge"
                  },
                  {
                    "#text": "https://lastfm.freetls.fastly.net/i/u/300x300/2a96cbd8b46e442fc41c2b86b821562f.png",
                    "size": "mega"
                  },
                  {
                    "#text": "https://lastfm.freetls.fastly.net/i/u/300x300/2a96cbd8b46e442fc41c2b86b821562f.png",
                    "size": ""
                  }
                ]
              },
              {
                "name": "Frank Ocean",
                "url": "https://www.last.fm/music/Frank+Ocean",
                "image": [
                  {
                    "#text": "https://lastfm.freetls.fastly.net/i/u/34s/2a96cbd8b46e442fc41c2b86b821562f.png",
                    "size": "small"
                  },
                  {
                    "#text": "https://lastfm.freetls.fastly.net/i/u/64s/2a96cbd8b46e442fc41c2b86b821562f.png",
                    "size": "medium"
                  },
                  {
                    "#text": "https://lastfm.freetls.fastly.net/i/u/174s/2a96cbd8b46e442fc41c2b86b821562f.png",
                    "size": "large"
                  },
                  {
                    "#text": "https://lastfm.freetls.fastly.net/i/u/300x300/2a96cbd8b46e442fc41c2b86b821562f.png",
                    "size": "extralarge"
                  },
                  {
                    "#text": "https://lastfm.freetls.fastly.net/i/u/300x300/2a96cbd8b46e442fc41c2b86b821562f.png",
                    "size": "mega"
                  },
                  {
                    "#text": "https://lastfm.freetls.fastly.net/i/u/300x300/2a96cbd8b46e442fc41c2b86b821562f.png",
                    "size": ""
                  }
                ]
              },
              {
                "name": "Majid Jordan",
                "url": "https://www.last.fm/music/Majid+Jordan",
                "image": [
                  {
                    "#text": "https://lastfm.freetls.fastly.net/i/u/34s/2a96cbd8b46e442fc41c2b86b821562f.png",
                    "size": "small"
                  },
                  {
                    "#text": "https://lastfm.freetls.fastly.net/i/u/64s/2a96cbd8b46e442fc41c2b86b821562f.png",
                    "size": "medium"
                  },
                  {
                    "#text": "https://lastfm.freetls.fastly.net/i/u/174s/2a96cbd8b46e442fc41c2b86b821562f.png",
                    "size": "large"
                  },
                  {
                    "#text": "https://lastfm.freetls.fastly.net/i/u/300x300/2a96cbd8b46e442fc41c2b86b821562f.png",
                    "size": "extralarge"
                  },
                  {
                    "#text": "https://lastfm.freetls.fastly.net/i/u/300x300/2a96cbd8b46e442fc41c2b86b821562f.png",
                    "size": "mega"
                  },
                  {
                    "#text": "https://lastfm.freetls.fastly.net/i/u/300x300/2a96cbd8b46e442fc41c2b86b821562f.png",
                    "size": ""
                  }
                ]
              }
            ]
          },
          "tags": {
            "tag": [
              {
                "name": "rnb",
                "url": "https://www.last.fm/tag/rnb"
              },
              {
                "name": "electronic",
                "url": "https://www.last.fm/tag/electronic"
              },
              {
                "name": "dubstep",
                "url": "https://www.last.fm/tag/dubstep"
              },
              {
                "name": "Canadian",
                "url": "https://www.last.fm/tag/Canadian"
              },
              {
                "name": "prog-rnb",
                "url": "https://www.last.fm/tag/prog-rnb"
              }
            ]
          },
          "bio": {
            "links": {
              "link": {
                "#text": "",
                "rel": "original",
                "href": "https://last.fm/music/The+Weeknd/+wiki"
              }
            },
            "published": "09 Jan 2011, 12:41",
            "summary": "Abel Makkonen Tesfaye (born February 16, 1990 in Scarborough, Ontario), popularly known as The Weeknd, is an R&B/pop/hip-hop singer from Toronto, Canada. He has been referred to as the songbird of his generation and the best musical talent since Michael Jackson throughout his career.\n\nThe Weeknd gained widespread critical acclaim for his three mixtapes, House of Balloons, Thursday, and Echoes of Silence, which he later compiled to make a remastered, three-disc album titled Trilogy after signing his record deal with Republic. <a href=\"https://www.last.fm/music/The+Weeknd\">Read more on Last.fm</a>",
            "content": "Abel Makkonen Tesfaye (born February 16, 1990 in Scarborough, Ontario), popularly known as The Weeknd, is an R&B/pop/hip-hop singer from Toronto, Canada. He has been referred to as the songbird of his generation and the best musical talent since Michael Jackson throughout his career.\n\nThe Weeknd gained widespread critical acclaim for his three mixtapes, House of Balloons, Thursday, and Echoes of Silence, which he later compiled to make a remastered, three-disc album titled Trilogy after signing his record deal with Republic. In 2013, he released Kiss Land, which was considered to be his debut studio album.\n\nIn 2014, he dropped “Often,” a remix of Beyonce’s “Drunk In Love,” and “King of the Fall.” The Weeknd released two songs in collaboration with the film Fifty Shades of Grey, with “Earned It” becoming his solo breakout hit.\n\nHis second studio album became highly-anticipated, with riveting singles like “The Hills” and “Can’t Feel My Face” leaving fans hungry for more. Beauty Behind the Madness was released on August 28, 2015.\n\nHis third studio album, Starboy, was released on November 25, 2016. The Daft Punk-assisted title track led the project as its first official single, released on Wednesday, September 21, 2016, before becoming his third number one track in the United States, as also his home country, Canada.\nThe effort was a commercial success, topping the Billboard 200 albums chart with over 348,000 copies sold in its first week, all eighteen tracks debuting on the Billboard Hot 100, receiving a GRAMMY Award for the Best Urban Contemporary Album category at the 60th annual ceremony, overall for the second time in his music career and being ranked as the third most popular album of 2017 in the U.S.\n\nHis debut EP, My Dear Melancholy,, released on March 30, 2018 includes themes revolving around his breakups with Bella Hadid during summer of 2016 and Selena Gomez in October 2017, respectively. With the lead single, “Call Out My Name”, the Canadian singer earned the largest first-day Spotify stream count of any song released in 2018 at that time and his eighth Top 10 entry on Hot 100.\n\nTesfaye’s fourth studio album (and his first in three years), After Hours was officially released on March 20, 2020, and is named after a 1985 movie directed by his idol, Martin Scorsese. It was primarily supported by November 2019-released singles “Heartless” and “Blinding Lights,” with the pair becoming his fourth and fifth #1 singles in the US and the latter his first #1 single in the UK. The successful promotional title track and “In Your Eyes” were also released as singles. <a href=\"https://www.last.fm/music/The+Weeknd\">Read more on Last.fm</a>. User-contributed text is available under the Creative Commons By-SA License; additional terms may apply."
          }
        }
      }
    ```
    
??? warning "Example response of an artist that doesnt exist"
    HTTP status: `404 NOT FOUND`

    ```
    https://ws.audioscrobbler.com/2.0/?method=artist.getinfo&artist=The+Weeknd+BUT+Fake&api_key=YOUR_API_KEY&format=json
    ```
    ```json
       {
        "error": 6,
        "message": "The artist you supplied could not be found",
        "links": []
      } 
    ```
