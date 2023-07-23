Get the top tags for this track on Last.fm, ordered by tag count.

No authentication required.

## Parameters
| Method | Type | Default | Required | Description
| ------ | ---- | ------- | -------- | -----------
| `track` | [string][string] | `none` | :white_check_mark: | The track name to fetch information for.
| `artist` | [string][string] | `none` | :negative_squared_cross_mark: | Narrow your search by specifying an artist.
| `limit` | [number][number] | 30 | :negative_squared_cross_mark: | The number of results to fetch per page.
| `page` | [number][number] | 1 | :negative_squared_cross_mark: | The page number to fetch.
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
    | track     | Hells Bells   |
    | api_key   | YOUR_API_KEY  |
    | format    | json          |

    HTTP status: `200 OK`

    ```
    https://ws.audioscrobbler.com/2.0/?method=track.search&track=Hells+Bells&api_key=YOUR_API_KEY&format=json
    ```
    ```json
    {
      "results": {
        "opensearch:Query": {
          "#text": "",
          "role": "request",
          "startPage": "1"
        },
        "opensearch:totalResults": "11634",
        "opensearch:startIndex": "0",
        "opensearch:itemsPerPage": "30",
        "trackmatches": {
          "track": [
            {
              "name": "Hells Bells",
              "artist": "AC/DC",
              "url": "https://www.last.fm/music/AC%2FDC/_/Hells+Bells",
              "streamable": "FIXME",
              "listeners": "796758",
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
                }
              ],
              "mbid": "b6411d6b-2dca-4004-8919-e8c27ff6b286"
            },
            {
              "name": "Hell's Bells",
              "artist": "Cary Ann Hearst",
              "url": "https://www.last.fm/music/Cary+Ann+Hearst/_/Hell%27s+Bells",
              "streamable": "FIXME",
              "listeners": "20485",
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
                }
              ],
              "mbid": "d0fd3d3b-ae2f-40d5-a5ac-d56c0d549dc7"
            },
            {
              "name": "Hell's Bells",
              "artist": "AC/DC",
              "url": "https://www.last.fm/music/AC%2FDC/_/Hell%27s+Bells",
              "streamable": "FIXME",
              "listeners": "19980",
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
                }
              ],
              "mbid": "c7c25302-69ab-4a9d-b967-23cbc6793854"
            },
            ... and 27 more
          ]
        },
        "@attr": {}
      }
    }
    ```

??? warning "Example response of an artist/track that doesnt exist"
    HTTP status: `200 OK`

    ```
    http://ws.audioscrobbler.com/2.0/?method=track.search&track=trackthatdoesntexist&api_key=YOUR_API_KEY&format=json
    ```
    ```json
    {
      "results": {
        "opensearch:Query": {
          "#text": "",
          "role": "request",
          "startPage": "1"
        },
        "opensearch:totalResults": "0",
        "opensearch:startIndex": "0",
        "opensearch:itemsPerPage": "30",
        "trackmatches": {
          "track": []
        },
        "@attr": {}
      }
    }
    ```

[string]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String
[number]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number
[key]: https://www.last.fm/api/account/create