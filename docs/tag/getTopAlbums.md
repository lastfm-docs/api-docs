Get the top albums tagged by this tag, ordered by tag count.

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

!!! Warning
    This API call returns 200 OK HTTP status codes even when the response contains an error.

## Examples
??? note "Example response"

    | Parameter | Value        |
    | --------- | ------------ |
    | tag       | metal        |
    | api_key   | YOUR_API_KEY |
    | format    | json         |

    HTTP status: `200 OK`

    ```
    https://ws.audioscrobbler.com/2.0/?method=tag.getTopAlbums&tag=metal&api_key=YOUR_API_KEY&format=json
    ```

    ```json
    {
      "albums": {
        "album": [
          {
            "name": "Ten Thousand Fists",
            "mbid": "d618f88f-a4a7-4028-a9e7-a2f3bcc3d9c3",
            "url": "https://www.last.fm/music/Disturbed",
            "artist": {
              "name": "Disturbed",
              "mbid": "dc75517c-d268-486d-bd5b-0eaff34eeef9",
              "url": "https://www.last.fm/music/Disturbed"
            },
            "image": [
              {
                "#text": "https://lastfm.freetls.fastly.net/i/u/34s/4c090f3226a7de3c21daaa92e2d4a416.png",
                "size": "small"
              },
              {
                "#text": "https://lastfm.freetls.fastly.net/i/u/64s/4c090f3226a7de3c21daaa92e2d4a416.png",
                "size": "medium"
              },
              {
                "#text": "https://lastfm.freetls.fastly.net/i/u/174s/4c090f3226a7de3c21daaa92e2d4a416.png",
                "size": "large"
              },
              {
                "#text": "https://lastfm.freetls.fastly.net/i/u/300x300/4c090f3226a7de3c21daaa92e2d4a416.png",
                "size": "extralarge"
              }
            ],
            "@attr": {
              "rank": "1"
            }
          },
          {
            "name": "City of Evil",
            "mbid": "4f7c1a59-92b1-4ba7-919f-b61a3b4b8d2a",
            "url": "https://www.last.fm/music/Avenged+Sevenfold",
            "artist": {
              "name": "Avenged Sevenfold",
              "mbid": "24e1b53c-3085-4581-8472-0b0088d2508c",
              "url": "https://www.last.fm/music/Avenged+Sevenfold"
            },
            "image": [
              {
                "#text": "https://lastfm.freetls.fastly.net/i/u/34s/50f59fc2dcff4345c3d492e1a71f634f.png",
                "size": "small"
              },
              {
                "#text": "https://lastfm.freetls.fastly.net/i/u/64s/50f59fc2dcff4345c3d492e1a71f634f.png",
                "size": "medium"
              },
              {
                "#text": "https://lastfm.freetls.fastly.net/i/u/174s/50f59fc2dcff4345c3d492e1a71f634f.png",
                "size": "large"
              },
              {
                "#text": "https://lastfm.freetls.fastly.net/i/u/300x300/50f59fc2dcff4345c3d492e1a71f634f.png",
                "size": "extralarge"
              }
            ],
            "@attr": {
              "rank": "2"
            }
          },
          {
            "name": "Indestructible",
            "mbid": "8bf771ef-dad7-4ff0-911a-d9661fee3df1",
            "url": "https://www.last.fm/music/Disturbed",
            "artist": {
              "name": "Disturbed",
              "mbid": "dc75517c-d268-486d-bd5b-0eaff34eeef9",
              "url": "https://www.last.fm/music/Disturbed"
            },
            "image": [
              {
                "#text": "https://lastfm.freetls.fastly.net/i/u/34s/4fe09361eb8a41e18eb06279bb8bceb6.png",
                "size": "small"
              },
              {
                "#text": "https://lastfm.freetls.fastly.net/i/u/64s/4fe09361eb8a41e18eb06279bb8bceb6.png",
                "size": "medium"
              },
              {
                "#text": "https://lastfm.freetls.fastly.net/i/u/174s/4fe09361eb8a41e18eb06279bb8bceb6.png",
                "size": "large"
              },
              {
                "#text": "https://lastfm.freetls.fastly.net/i/u/300x300/4fe09361eb8a41e18eb06279bb8bceb6.png",
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
          "totalPages": "585",
          "total": "29201"
        }
      }
    }
    ```

??? warning "Example response of a tag that doesn't exist"
    HTTP status: `200 OK`

    ```
    https://ws.audioscrobbler.com/2.0/?method=tag.getTopAlbums&tag=thistagdoesntexist&api_key=YOUR_API_KEY&format=json
    ```
    ```json
    {
      "albums": {
        "album": [],
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