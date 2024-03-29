Get the tags applied by an individual user to a track on Last.fm.

No authentication required.

## Parameters
| Method | Type | Default | Required | Description
| ------ | ---- | ------- | -------- | -----------
| `artist` | [string][string] | `none` | :white_check_mark: * | The artist name to fetch information for.
| `track` | [string][string] | `none` | :white_check_mark: * | The track name to fetch information for.
| `user` | [string][string] | `none` | :white_check_mark: ** | The user to look up the tags for.
| `mbid` | [string][string] | `none` | :negative_squared_cross_mark: | The artist's MusicBrainz ID.
| `autocorrect` | [number][number] | 0 | :negative_squared_cross_mark: | Transform misspelled artist names into correct artist names, returning the correct version instead. The corrected artist name will be returned in the response.
| `api_key` | [key][key] | `none` | :white_check_mark: | A Last.fm API key.

\* Required unless you are using a MusicBrainz ID for the artist/track.  
\** Required unless the method is called in authenticated mode.

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
    https://ws.audioscrobbler.com/2.0/?method=track.getTags&artist=AC/DC&track=Hells+Bells&user=RJ&api_key=YOUR_API_KEY&format=json
    ```
    ```json
    {
      "tags": {
        "tag": [
          {
            "name": "guitar",
            "url": "https://www.last.fm/tag/guitar"
          },
          {
            "name": "metal",
            "url": "https://www.last.fm/tag/metal"
          },
          {
            "name": "rock",
            "url": "https://www.last.fm/tag/rock"
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
    https://ws.audioscrobbler.com/2.0/?method=track.getTags&artist=artistthatdoesntexist&track=trackthatdoesntexist&user=solelychloe&api_key=YOUR_API_KEY&format=json
    ```
    ```json
    {
      "error": 6,
      "message": "Track not found",
      "links": []
    }
    ```


[string]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String
[number]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number
[key]: https://www.last.fm/api/account/create