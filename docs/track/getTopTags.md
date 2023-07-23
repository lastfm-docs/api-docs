Get the top tags for this track on Last.fm, ordered by tag count.

No authentication required.

## Parameters
| Method | Type | Default | Required | Description
| ------ | ---- | ------- | -------- | -----------
| `artist` | [string][string] | `none` | :white_check_mark: * | The artist name to fetch information for.
| `track` | [string][string] | `none` | :white_check_mark: * | The track name to fetch information for.
| `mbid` | [string][string] | `none` | :negative_squared_cross_mark: | The artist's MusicBrainz ID.
| `autocorrect` | [number][number] | 0 | :negative_squared_cross_mark: | Transform misspelled artist names into correct artist names, returning the correct version instead. The corrected artist name will be returned in the response.
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
??? note "Example response"

    | Parameter | Value        |
    | --------- | ------------ |
    | artist    | AC/DC        |
    | track     | Hells Bells  |
    | api_key   | YOUR_API_KEY |
    | format    | json         |

    HTTP status: `200 OK`

    ```
    https://ws.audioscrobbler.com/2.0/?method=track.getTopTags&artist=AC/DC&track=Hells+Bells&api_key=YOUR_API_KEY&format=json
    ```
    ```json
    {
      "toptags": {
        "tag": [
          {
            "count": 100,
            "name": "hard rock",
            "url": "https://www.last.fm/tag/hard+rock"
          },
          {
            "count": 58,
            "name": "rock",
            "url": "https://www.last.fm/tag/rock"
          },
          {
            "count": 53,
            "name": "classic rock",
            "url": "https://www.last.fm/tag/classic+rock"
          },
          {
            "count": 27,
            "name": "ACDC",
            "url": "https://www.last.fm/tag/ACDC"
          },
          {
            "count": 25,
            "name": "heavy metal",
            "url": "https://www.last.fm/tag/heavy+metal"
          },
          {
            "count": 14,
            "name": "80s",
            "url": "https://www.last.fm/tag/80s"
          },
          {
            "count": 12,
            "name": "AC/DC",
            "url": "https://www.last.fm/tag/AC%2FDC"
          },
          {
            "count": 11,
            "name": "metal",
            "url": "https://www.last.fm/tag/metal"
          },
          {
            "count": 6,
            "name": "australian",
            "url": "https://www.last.fm/tag/australian"
          },
          {
            "count": 6,
            "name": "guitar",
            "url": "https://www.last.fm/tag/guitar"
          },
          {
            "count": 5,
            "name": "Rock and Roll",
            "url": "https://www.last.fm/tag/Rock+and+Roll"
          },
          {
            "count": 5,
            "name": "hells bells",
            "url": "https://www.last.fm/tag/hells+bells"
          },
          {
            "count": 4,
            "name": "1980",
            "url": "https://www.last.fm/tag/1980"
          },
          {
            "count": 3,
            "name": "70s",
            "url": "https://www.last.fm/tag/70s"
          },
          {
            "count": 3,
            "name": "Supernatural",
            "url": "https://www.last.fm/tag/Supernatural"
          },
          {
            "count": 3,
            "name": "blues rock",
            "url": "https://www.last.fm/tag/blues+rock"
          },
          {
            "count": 3,
            "name": "heavy rock",
            "url": "https://www.last.fm/tag/heavy+rock"
          },
          {
            "count": 3,
            "name": "favorites",
            "url": "https://www.last.fm/tag/favorites"
          },
          {
            "count": 3,
            "name": "classic metal",
            "url": "https://www.last.fm/tag/classic+metal"
          },
          {
            "count": 2,
            "name": "rock n roll",
            "url": "https://www.last.fm/tag/rock+n+roll"
          },
          {
            "count": 2,
            "name": "Awesome",
            "url": "https://www.last.fm/tag/Awesome"
          },
          {
            "count": 2,
            "name": "seen live",
            "url": "https://www.last.fm/tag/seen+live"
          },
          {
            "count": 2,
            "name": "australia",
            "url": "https://www.last.fm/tag/australia"
          },
          {
            "count": 2,
            "name": "live",
            "url": "https://www.last.fm/tag/live"
          },
          {
            "count": 2,
            "name": "ac dc",
            "url": "https://www.last.fm/tag/ac+dc"
          },
          {
            "count": 2,
            "name": "classic",
            "url": "https://www.last.fm/tag/classic"
          },
          {
            "count": 2,
            "name": "Hard",
            "url": "https://www.last.fm/tag/Hard"
          },
          {
            "count": 2,
            "name": "10 of 10 stars",
            "url": "https://www.last.fm/tag/10+of+10+stars"
          },
          {
            "count": 2,
            "name": "hardrock",
            "url": "https://www.last.fm/tag/hardrock"
          },
          {
            "count": 2,
            "name": "Ac-Dc",
            "url": "https://www.last.fm/tag/Ac-Dc"
          },
          {
            "count": 2,
            "name": "alternative",
            "url": "https://www.last.fm/tag/alternative"
          },
          {
            "count": 1,
            "name": "heavy",
            "url": "https://www.last.fm/tag/heavy"
          },
          {
            "count": 1,
            "name": "bells",
            "url": "https://www.last.fm/tag/bells"
          },
          {
            "count": 1,
            "name": "male vocalist",
            "url": "https://www.last.fm/tag/male+vocalist"
          },
          {
            "count": 1,
            "name": "angus young",
            "url": "https://www.last.fm/tag/angus+young"
          },
          {
            "count": 1,
            "name": "back in black",
            "url": "https://www.last.fm/tag/back+in+black"
          }
        ],
        "@attr": {
          "artist": "AC/DC",
          "track": "Hells Bells"
        }
      }
    }
    ```

??? warning "Example response of an artist/track that doesnt exist"
    HTTP status: `200 OK`

    ```
    http://ws.audioscrobbler.com/2.0/?method=track.getTopTags&artist=Metallica&track=Hells+Bells&api_key=YOUR_API_KEY&format=json
    ```
    ```json
    {
      "toptags": {
        "tag": [],
        "@attr": {
          "artist": "Metallica",
          "track": "Hells Bells"
        }
      }
    }
    ```


[string]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String
[number]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number
[key]: https://www.last.fm/api/account/create