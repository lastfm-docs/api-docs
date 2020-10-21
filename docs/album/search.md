Get the top tags for an album on Last.fm, ordered by popularity.

No authentication required.

## Parameters

| Method    | Type                                                                                              | Default | Required                      | Description                                 |
| --------- | ------------------------------------------------------------------------------------------------- | ------- | ----------------------------- | ------------------------------------------- |
| `limit`   | [number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) | 30      | :negative_squared_cross_mark: | The artist which's album should be fetched. |
| `page`    | [number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) | 1       | :negative_squared_cross_mark: | The album that should be fetched.           |
| `album`   | [string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) | `none`  | :white_check_mark:            | The album's musicbrainz id.                 |
| `api_key` | [token](https://www.last.fm/api/account/create)                                                   | `none`  | :white_check_mark:            | A Last.fm API key.                          |

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
    | album     | Greatest Hits |
    | api_key   | YOUR_API_KEY  |
    | page      | 2             |
    | format    | json          |

    HTTP status: `200 OK`

    ```
    http://ws.audioscrobbler.com/2.0/?method=album.search&album=Greatest%20Hits&page=2&api_key=YOUR_API_KEY&format=json
    ```

    ```json
    {
    "results": {
        "opensearch:Query": {
        "#text": "",
        "role": "request",
        "searchTerms": "greatest hits",
        "startPage": "2"
        },
        "opensearch:totalResults": "1068391",
        "opensearch:startIndex": "50",
        "opensearch:itemsPerPage": "50",
        "album": [
        {
          "name": "Greatest Hits",
          "artist": "Simply Red",
          "url": "https://www.last.fm/music/Simply+Red/Greatest+Hits",
          "image": [
            {
              "#text": "https://lastfm.freetls.fastly.net/i/u/34s/d6a2c56c7b6295e99c8213987363d8ff.png",
              "size": "small"
            },
            {
              "#text": "https://lastfm.freetls.fastly.net/i/u/64s/d6a2c56c7b6295e99c8213987363d8ff.png",
              "size": "medium"
            },
            {
              "#text": "https://lastfm.freetls.fastly.net/i/u/174s/d6a2c56c7b6295e99c8213987363d8ff.png",
              "size": "large"
            },
            {
              "#text": "https://lastfm.freetls.fastly.net/i/u/300x300/d6a2c56c7b6295e99c8213987363d8ff.png",
              "size": "extralarge"
            }
          ],
          "streamable": "0",
          "mbid": "fb871fa5-23f2-387a-be2a-c3f1ad074393"
        },
        ]

        "@attr": {
        "for": "greatest hits"
        }
      }
    }
    ```

??? warning "Example response of an album that doesnt exist"
    HTTP status: `200 OK`

    ```
    http://ws.audioscrobbler.com/2.0/?method=album.search&album=albumthatdoesntexist&page=2&api_key=YOUR_API_KEY&format=json
    ```
    ```json
    {
        "results": {
        "opensearch:Query": {
        "#text": "",
        "role": "request",
        "searchTerms": "albumthatdoesntexist",
        "startPage": "2"
        },
        "opensearch:totalResults": "0",
        "opensearch:startIndex": "50",
        "opensearch:itemsPerPage": "50",
        "albummatches": {
        "album": []
        },
        "@attr": {
        "for": "albumthatdoesntexist"
        }
      }
    }
    ```
