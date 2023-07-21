Get the tags applied by an individual user to an album on Last.fm.

No authentication required.

## Parameters

| Method | Type | Default | Required | Description 
| ------ | ---- | ------- | -------- | -----------
| `artist` | [string][string] | `none` | :white_check_mark: \* | The artist which's album should be fetched.
| `album` | [string][string] | `none` | :white_check_mark: \* | The album that should be fetched.
| `mbid` | [string][string] | `none` | :negative_squared_cross_mark: | The album's MusicBrainz ID.
| `autocorrect` | [number][number] | 0 | :negative_squared_cross_mark: | Automatically corrects any mistakes in the artist's name.
| `user` | [string][string] | `none` | :negative_squared_cross_mark: | If not in authenticated mode, this field should be provided with the user that should be looked up.
| `api_key` | [key][key] | `none` | :white_check_mark: | A Last.fm API key.

\* Required unless you are using a MusicBrainz ID for the album.

## Responses

Errors:


- 6 : Invalid parameters - Your request is missing a required parameter
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
    | artist    | Metallica     |
    | album     | Metallica     |
    | user      | Burdayy       |
    | api_key   | YOUR_API_KEY  |
    | format    | json          |

    HTTP status: `200 OK`

    ```
    https://ws.audioscrobbler.com/2.0/?method=album.getTags&artist=Metallica&album=Metallica&user=Burdayy&api_key=YOUR_API_KEY&format=json
    ```

    ```json
    {
        "tags": {
            "tag": [
            {
                "name": "classic metal",
                "url": "https://www.last.fm/tag/classic+metal"
            }
            ],
            "@attr": {
            "artist": "Metallica",
            "album": "Metallica"
            }
        }
    }

    ```

??? warning "Example response of an artist/album that doesnt exist"
    HTTP status: `200 OK`

    ```
    https://ws.audioscrobbler.com/2.0/?method=album.gettags&artist=ArtistThatDoesntExist&album=metallica&user=burdayy&api_key=YOUR_API_KEY&format=json
    ```
    ```json
    {
        "error": 6,
        "message": "Album not found",
        "links": []
    }
    ```
    
??? warning "Example response of an user that doesnt exist"
    HTTP status: `200 OK`

    ```
    https://ws.audioscrobbler.com/2.0/?method=album.gettags&artist=metallica&album=metallica&user=UserThatDoesntExist&api_key=YOUR_API_KEY&format=json
    ```
    ```json
    {
        "error": 6,
        "message": "User not found",
        "links": []
    }
    ```

[string]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String
[number]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number
[key]: https://www.last.fm/api/account/create