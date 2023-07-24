Use the Last.fm corrections data to check whether the supplied artist has a correction to a canonical artist.

No authentication required.

## Parameters
| Method | Type | Default | Required | Description 
| ------ | ---- | ------- | -------- | -----------
| `artist` | [string][string] | `none` | :white_check_mark: | The artist name to correct.
| `api_key` | [key][key] | `none` | :white_check_mark: | A Last.fm API key.

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

    | Parameter | Value         |
    | --------- | ------------- |
    | artist    | Avici         |
    | api_key   | YOUR_API_KEY  |
    | format    | json          |

    HTTP status: `200 OK`

    ```
    https://ws.audioscrobbler.com/2.0/?method=artist.getCorrection&artist=Avici&api_key=YOUR_API_KEY&format=json
    ```

    ```json
    {
      "corrections": {
        "correction": {
          "artist": {
            "name": "Avicii",
            "mbid": "c85cfd6b-b1e9-4a50-bd55-eb725f04f7d5",
            "url": "https://www.last.fm/music/Avicii"
          },
          "@attr": {
            "index": "0"
          }
        }
      }
    }
    ```

??? warning "Example response of an artist/track that doesnt exist"
    HTTP status: `200 OK`

    ```
    https://ws.audioscrobbler.com/2.0/?method=artist.getCorrection&artist=artistdoesntexist&api_key=YOUR_API_KEY&format=json
    ```
    ```json
    {
      	"corrections": "\n                "
    }
    ```

[string]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String
[key]: https://www.last.fm/api/account/create