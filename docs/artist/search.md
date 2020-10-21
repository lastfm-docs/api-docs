Search for an artist by name, ordered by relevance.

No authentication required.

## Parameters

| Method    | Type                                                                                              | Default | Required                      | Description                                 |
| --------- | ------------------------------------------------------------------------------------------------- | ------- | ----------------------------- | ------------------------------------------- |
| `limit`   | [number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) | 30      | :negative_squared_cross_mark: | The artist which's album should be fetched. |
| `page`    | [number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) | 1       | :negative_squared_cross_mark: | The album that should be fetched.           |
| `artist`   | [string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) | `none`  | :white_check_mark:            | The artist's name            |
| `api_key` | [token](https://www.last.fm/api/account/create)                                                   | `none`  | :white_check_mark:            | A Last.fm API key.                          |

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
    | artist    | Greatest Hits |
    | api_key   | YOUR_API_KEY  |
    | format    | json          |

    HTTP status: `200 OK`

    ```
    http://ws.audioscrobbler.com/2.0/?method=artist.search&artist=Rammstein&api_key=YOUR_API_KEY&format=json
    ```

    ```json
    {
      "results": {
        "opensearch:Query": {
          "#text": "",
          "role": "request",
          "searchTerms": "rammstein",
          "startPage": "1"
        },
        "opensearch:totalResults": "13809",
        "opensearch:startIndex": "0",
        "opensearch:itemsPerPage": "30",
        "artistmatches": {
          "artist": [
            {
              "name": "Rammstein",
              "listeners": "1913191",
              "mbid": "b2d122f9-eadb-4930-a196-8f221eeb0c66",
              "url": "https://www.last.fm/music/Rammstein",
              "streamable": "0",
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
                }
              ]
            }
          ]
        },
        "@attr": {
          "for": "rammstein"
        }
      }
    }
    ```

??? warning "Example response of an artist that doesnt exist"
    HTTP status: `200 OK`

    ```
    http://ws.audioscrobbler.com/2.0/?method=artist.search&artist=artistthatdoesntexist&api_key=YOUR_API_KEY&format=json
    ```
    ```json
    {
      "results": {
        "opensearch:Query": {
          "#text": "",
          "role": "request",
          "searchTerms": "artistthatdoesntexisthsjdkghkjdfgh",
          "startPage": "1"
        },
        "opensearch:totalResults": "0",
        "opensearch:startIndex": "0",
        "opensearch:itemsPerPage": "30",
        "artistmatches": {
          "artist": [
            
          ]
        },
        "@attr": {
          "for": "artistthatdoesntexisthsjdkghkjdfgh"
        }
      }
    }
    ```
