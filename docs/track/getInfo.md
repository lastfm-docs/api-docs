Get the metadata for a track on Last.fm using the artist/track name or a MusicBrainz ID.

No authentication required.

## Parameters
| Method | Type | Default | Required | Description
| ------ | ---- | ------- | -------- | -----------
| `artist` | [string][string] | `none` | :white_check_mark: \* | The artist name to fetch information for.
| `track` | [string][string] | `none` | :white_check_mark: \* | The track name to fetch information for.
| `mbid` | [string][string] | `none` | :negative_squared_cross_mark: | The artist's MusicBrainz ID.
| `autocorrect` | [number][number] | 0 | :negative_squared_cross_mark: | Transform misspelled artist names into correct artist names, returning the correct version instead. The corrected artist name will be returned in the response.
| `username` | [string][string] | `none` | :negative_squared_cross_mark: | The username for the context of the request. If supplied, the user's playcount for this track and whether they have loved the track is included in the response.
| `api_key` | [key][key] | `none` | :white_check_mark: | A Last.fm API key.

\* Required unless you are using a MusicBrainz ID for the artist/track.

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

!!! Warning
    This API call returns 200 OK HTTP status codes even when the response contains an error.

## Examples

??? note "Example response with user parameter"

    | Parameter | Value           |
    | --------- | -------------   |
    | track     | One Step Closer |
    | artist    | Linkin Park     |
    | username  | solelychloe     |
    | api_key   | YOUR_API_KEY    |
    | format    | json            |

    HTTP status: `200 OK`

    ```
    https://ws.audioscrobbler.com/2.0/?method=track.getInfo&artist=Linkin Park&track=One Step Closer&username=solelychloe&api_key=YOUR_API_KEY&format=json
    ```
    ```json
    {
      "track": {
        "name": "One Step Closer",
        "mbid": "30cb03f3-bd95-43b0-9d41-6d75e13cd353",
        "url": "https://www.last.fm/music/Linkin+Park/_/One+Step+Closer",
        "duration": "157000",
        "streamable": {
          "#text": "0",
          "fulltrack": "0"
        },
        "listeners": "1315650",
        "playcount": "11022708",
        "artist": {
          "name": "Linkin Park",
          "mbid": "f59c5520-5f46-4d2c-b2c4-822eabf53419",
          "url": "https://www.last.fm/music/Linkin+Park"
        },
        "album": {
          "artist": "Linkin Park",
          "title": "Road To Revolution: Live at Milton Keynes",
          "mbid": "9c7b6839-ce71-3741-a107-2f5dc678f4b4",
          "url": "https://www.last.fm/music/Linkin+Park/Road+To+Revolution:+Live+at+Milton+Keynes",
          "image": [
            {
              "#text": "https://lastfm.freetls.fastly.net/i/u/34s/1f922f8eb093037a30faa1c666a84c78.png",
              "size": "small"
            },
            {
              "#text": "https://lastfm.freetls.fastly.net/i/u/64s/1f922f8eb093037a30faa1c666a84c78.png",
              "size": "medium"
            },
            {
              "#text": "https://lastfm.freetls.fastly.net/i/u/174s/1f922f8eb093037a30faa1c666a84c78.png",
              "size": "large"
            },
            {
              "#text": "https://lastfm.freetls.fastly.net/i/u/300x300/1f922f8eb093037a30faa1c666a84c78.png",
              "size": "extralarge"
            }
          ],
          "@attr": {
            "position": "1"
          }
        },
        "userplaycount": "36",
        "userloved": "0",
        "toptags": {
          "tag": [
            {
              "name": "Nu Metal",
              "url": "https://www.last.fm/tag/Nu+Metal"
            },
            {
              "name": "rock",
              "url": "https://www.last.fm/tag/rock"
            },
            {
              "name": "Linkin Park",
              "url": "https://www.last.fm/tag/Linkin+Park"
            },
            {
              "name": "alternative rock",
              "url": "https://www.last.fm/tag/alternative+rock"
            },
            {
              "name": "alternative",
              "url": "https://www.last.fm/tag/alternative"
            }
          ]
        },
        "wiki": {
          "published": "14 Apr 2009, 16:25",
          "summary": "\"One Step Closer\" is the debut single by the nu metal band Linkin Park released in 2000 and the second track of their debut album, Hybrid Theory. It is also the song that catapulted the band to stardom, especially towards the rock audience, as well as one of the band's well-known songs. The song reached #79 on the Hot 100 on February 20, 2001.\n\nAccording to the One Step Closer Songfacts, the vocals were recorded in Mike Shinoda's flat one night while an angry neighbor hammered on the wall. <a href=\"https://www.last.fm/music/Linkin+Park/_/One+Step+Closer\">Read more on Last.fm</a>.",
          "content": "\"One Step Closer\" is the debut single by the nu metal band Linkin Park released in 2000 and the second track of their debut album, Hybrid Theory. It is also the song that catapulted the band to stardom, especially towards the rock audience, as well as one of the band's well-known songs. The song reached #79 on the Hot 100 on February 20, 2001.\n\nAccording to the One Step Closer Songfacts, the vocals were recorded in Mike Shinoda's flat one night while an angry neighbor hammered on the wall. He couldn't hear the actual music, just Chester Bennington screaming into the microphone.\n\nUntil 2007, Linkin Park has closed every concert to date with \"One Step Closer\", excluding Live 8, their live performance at Summer Sonic.\n\nDuring the 2001 MTV VMA performance of the song, the band had The X-Ecutioners do an extended break before the bridge. This part was somewhat similar to the atmosphere on the remix, with synth parts and faint vocal parts being scratched.\n\nFrom 2003 to 2007, performances of the song include a verse originally sung by Jonathan Davis in the Reanimation remix of the song before the \"Shut up when I'm talking to you!\" bridge. At the end of the verse, Bennington then repeats the line \"Blood is pouring\" while the song builds up to the bridge.\nOn occasion, Shinoda sings \"Blood is pouring\" under Bennington's screaming during this part, as is done by Jonathan Davis on the remix. This is half-done on the performance at 2004's Rock am Ring (in that Shinoda only sings the part during the second half of the bridge) and fully done during a performance during 2003's Projekt Revolution tour, which was recorded and included on the \"Faint\" single and is available as a bonus track for Reanimation when purchased on iTunes. On the single cover, it is called '\"One Step Closer\" (Reanimated Live)'. During the 2006 live performances in Japan, the Reanimation bridge was played with the main riff of the song.\n\nDuring the band's 2007 tour, \"One Step Closer\" became the opening song of Linkin Park's performances, and the Reanimation verse was removed. It also featured a new, extended intro featuring Mike Shinoda on rhythm guitar.\n\nIn 2008 it became a new extended outro, and sometimes it was performed as the last song. <a href=\"https://www.last.fm/music/Linkin+Park/_/One+Step+Closer\">Read more on Last.fm</a>. User-contributed text is available under the Creative Commons By-SA License; additional terms may apply."
        }
      }
    }
    ```

??? note "Example response without user parameter"

    | Parameter | Value           |
    | --------- | -------------   |
    | track     | One Step Closer |
    | artist    | Linkin Park     |
    | api_key   | YOUR_API_KEY    |
    | format    | json            |

    HTTP status: `200 OK`

    ```
    https://ws.audioscrobbler.com/2.0/?method=track.getInfo&artist=Linkin Park&track=One Step Closer&api_key=YOUR_API_KEY&format=json
    ```
    ```json
    {
      "track": {
        "name": "One Step Closer",
        "mbid": "30cb03f3-bd95-43b0-9d41-6d75e13cd353",
        "url": "https://www.last.fm/music/Linkin+Park/_/One+Step+Closer",
        "duration": "157000",
        "streamable": {
          "#text": "0",
          "fulltrack": "0"
        },
        "listeners": "1315650",
        "playcount": "11022708",
        "artist": {
          "name": "Linkin Park",
          "mbid": "f59c5520-5f46-4d2c-b2c4-822eabf53419",
          "url": "https://www.last.fm/music/Linkin+Park"
        },
        "album": {
          "artist": "Linkin Park",
          "title": "Road To Revolution: Live at Milton Keynes",
          "mbid": "9c7b6839-ce71-3741-a107-2f5dc678f4b4",
          "url": "https://www.last.fm/music/Linkin+Park/Road+To+Revolution:+Live+at+Milton+Keynes",
          "image": [
            {
              "#text": "https://lastfm.freetls.fastly.net/i/u/34s/1f922f8eb093037a30faa1c666a84c78.png",
              "size": "small"
            },
            {
              "#text": "https://lastfm.freetls.fastly.net/i/u/64s/1f922f8eb093037a30faa1c666a84c78.png",
              "size": "medium"
            },
            {
              "#text": "https://lastfm.freetls.fastly.net/i/u/174s/1f922f8eb093037a30faa1c666a84c78.png",
              "size": "large"
            },
            {
              "#text": "https://lastfm.freetls.fastly.net/i/u/300x300/1f922f8eb093037a30faa1c666a84c78.png",
              "size": "extralarge"
            }
          ],
          "@attr": {
            "position": "1"
          }
        },
        "toptags": {
          "tag": [
            {
              "name": "Nu Metal",
              "url": "https://www.last.fm/tag/Nu+Metal"
            },
            {
              "name": "rock",
              "url": "https://www.last.fm/tag/rock"
            },
            {
              "name": "Linkin Park",
              "url": "https://www.last.fm/tag/Linkin+Park"
            },
            {
              "name": "alternative rock",
              "url": "https://www.last.fm/tag/alternative+rock"
            },
            {
              "name": "alternative",
              "url": "https://www.last.fm/tag/alternative"
            }
          ]
        },
        "wiki": {
          "published": "14 Apr 2009, 16:25",
          "summary": "\"One Step Closer\" is the debut single by the nu metal band Linkin Park released in 2000 and the second track of their debut album, Hybrid Theory. It is also the song that catapulted the band to stardom, especially towards the rock audience, as well as one of the band's well-known songs. The song reached #79 on the Hot 100 on February 20, 2001.\n\nAccording to the One Step Closer Songfacts, the vocals were recorded in Mike Shinoda's flat one night while an angry neighbor hammered on the wall. <a href=\"https://www.last.fm/music/Linkin+Park/_/One+Step+Closer\">Read more on Last.fm</a>.",
          "content": "\"One Step Closer\" is the debut single by the nu metal band Linkin Park released in 2000 and the second track of their debut album, Hybrid Theory. It is also the song that catapulted the band to stardom, especially towards the rock audience, as well as one of the band's well-known songs. The song reached #79 on the Hot 100 on February 20, 2001.\n\nAccording to the One Step Closer Songfacts, the vocals were recorded in Mike Shinoda's flat one night while an angry neighbor hammered on the wall. He couldn't hear the actual music, just Chester Bennington screaming into the microphone.\n\nUntil 2007, Linkin Park has closed every concert to date with \"One Step Closer\", excluding Live 8, their live performance at Summer Sonic.\n\nDuring the 2001 MTV VMA performance of the song, the band had The X-Ecutioners do an extended break before the bridge. This part was somewhat similar to the atmosphere on the remix, with synth parts and faint vocal parts being scratched.\n\nFrom 2003 to 2007, performances of the song include a verse originally sung by Jonathan Davis in the Reanimation remix of the song before the \"Shut up when I'm talking to you!\" bridge. At the end of the verse, Bennington then repeats the line \"Blood is pouring\" while the song builds up to the bridge.\nOn occasion, Shinoda sings \"Blood is pouring\" under Bennington's screaming during this part, as is done by Jonathan Davis on the remix. This is half-done on the performance at 2004's Rock am Ring (in that Shinoda only sings the part during the second half of the bridge) and fully done during a performance during 2003's Projekt Revolution tour, which was recorded and included on the \"Faint\" single and is available as a bonus track for Reanimation when purchased on iTunes. On the single cover, it is called '\"One Step Closer\" (Reanimated Live)'. During the 2006 live performances in Japan, the Reanimation bridge was played with the main riff of the song.\n\nDuring the band's 2007 tour, \"One Step Closer\" became the opening song of Linkin Park's performances, and the Reanimation verse was removed. It also featured a new, extended intro featuring Mike Shinoda on rhythm guitar.\n\nIn 2008 it became a new extended outro, and sometimes it was performed as the last song. <a href=\"https://www.last.fm/music/Linkin+Park/_/One+Step+Closer\">Read more on Last.fm</a>. User-contributed text is available under the Creative Commons By-SA License; additional terms may apply."
        }
      }
    }
    ```
    
??? warning "Example response of a track/artist that doesnt exist"
    HTTP status: `200 OK`

    ```
    https://ws.audioscrobbler.com/2.0/?method=track.getInfo&artist=Fake+Artist&track=Fake+Track&api_key=YOUR_API_KEY&format=json
    ```
    ```json
    {
      "track": {
        "name": "Fake Track",
        "url": "https://www.last.fm/music/Fake+Artist/_/Fake+Track",
        "duration": "0",
        "streamable": {
          "#text": "0",
          "fulltrack": "0"
        },
        "listeners": "2",
        "playcount": "4",
        "artist": {
          "name": "Fake Artist",
          "url": "https://www.last.fm/music/Fake+Artist"
        },
        "toptags": {
          "tag": []
        }
      }
    } 
    ```

[string]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String
[number]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number
[key]: https://www.last.fm/api/account/create