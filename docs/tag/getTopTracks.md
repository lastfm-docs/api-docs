Get the top tracks tagged by this tag, ordered by tag count.

No authentication required.

## Parameters
| Method | Type | Default | Required | Description 
| ------ | ---- | ------- | -------- | -----------
| `tag` | [string][string] | `none` | :white_check_mark: | The tag name to search information for.
| `limit` | [number][number] | 50 | :negative_squared_cross_mark: | The number of results to fetch per page.
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

## Examples
??? note "Example response"

    | Parameter | Value        |
    | --------- | ------------ |
    | tag       | metal        |
    | api_key   | YOUR_API_KEY |
    | format    | json         |

    HTTP status: `200 OK`

    ```
    https://ws.audioscrobbler.com/2.0/?method=tag.getTopTracks&tag=metal&api_key=YOUR_API_KEY&format=json
    ```

    ```json
    {
      "tracks": {
        "track": [
          {
            "name": "Chop Suey!",
            "duration": "208",
            "mbid": "d758947d-d667-430b-900d-2abb110f63aa",
            "url": "https://www.last.fm/music/System+of+a+Down/_/Chop+Suey%21",
            "streamable": {
              "#text": "0",
              "fulltrack": "0"
            },
            "artist": {
              "name": "System of a Down",
              "mbid": "cc0b7089-c08d-4c10-b6b0-873582c17fd6",
              "url": "https://www.last.fm/music/System+of+a+Down"
            },
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
            "@attr": {
              "rank": "1"
            }
          },
          {
            "name": "In the End",
            "duration": "216",
            "mbid": "9d70086c-5d7a-4e7f-b1ed-c53c4b11310f",
            "url": "https://www.last.fm/music/Linkin+Park/_/In+the+End",
            "streamable": {
              "#text": "0",
              "fulltrack": "0"
            },
            "artist": {
              "name": "Linkin Park",
              "mbid": "f59c5520-5f46-4d2c-b2c4-822eabf53419",
              "url": "https://www.last.fm/music/Linkin+Park"
            },
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
            "@attr": {
              "rank": "2"
            }
          },
          {
            "name": "Numb",
            "duration": "191",
            "mbid": "f3217a42-bb14-4191-8c2e-c5e5413467be",
            "url": "https://www.last.fm/music/Linkin+Park/_/Numb",
            "streamable": {
              "#text": "0",
              "fulltrack": "0"
            },
            "artist": {
              "name": "Linkin Park",
              "mbid": "f59c5520-5f46-4d2c-b2c4-822eabf53419",
              "url": "https://www.last.fm/music/Linkin+Park"
            },
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
            "@attr": {
              "rank": "3"
            }
          },
          ... and 47 more
        ],
        "@attr": {
          "tag": "metal",
          "page": "1",
          "perPage": "50",
          "totalPages": "3316",
          "total": "165756"
        }
      }
    }
    ```

??? warning "Example response of a tag that doesn't exist"
    HTTP status: `200 OK`

    ```
    https://ws.audioscrobbler.com/2.0/?method=tag.getTopTracks&tag=thistagdoesntexist&api_key=YOUR_API_KEY&format=json
    ```
    ```json
    {
      "tracks": {
        "track": [],
        "@attr": {
          "tag": "thistagdoesntexist",
          "page": "1",
          "perPage": "50",
          "totalPages": "0",
          "total": "0"
        }
      }
    }
    ```

[string]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String
[number]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number
[key]: https://www.last.fm/api/account/create