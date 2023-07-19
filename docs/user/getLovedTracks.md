Returns a list of the tracks loved scrobbled by this user.

No authentication required.

## Parameters
| Method | Type | Default | Required | Description 
| ------ | ---- | ------- | -------- | -----------
| `user` | [string][string] | `none` | :white_check_mark: | The last.fm username to fetch the loved tracks of.
| `limit` | [number][number] | 50 | :negative_squared_cross_mark: | The number of results to fetch per page. Maximum is 1000.
| `page` | [number][number] | 1 | :negative_squared_cross_mark: | The page number to fetch.
| `api_key` | [key][key] | `none` | :white_check_mark: | A Last.fm API key.

## Responses

Errors:

- 6 : Invalid parameters - Your request is missing a required parameter
- 8 : Operation failed - Something else went wrong
- 9 : Invalid session key - Please re-authenticate
- 10 : Invalid API key - You must be granted a valid key by last.fm
- 11 : Service Offline - This service is temporarily offline. Try again later.
- 13 : Invalid method signature supplied
- 16 : There was a temporary error processing your request. Please try again
- 17 : Login required - Requested profile might not have privacy set to public.
- 26 : Suspended API key - Access for your account has been suspended, please contact Last.fm
- 29 : Rate limit exceeded - Your IP has made too many requests in a short period

## Examples

??? note "Example Response"

    | Parameter | Value            |
    |-----------|------------------|
    | username  | TyphoonasNorABot |
    | limit     | 1                |
    | format    | json             |
    
    HTTP status: `200 OK`

    ```
    https://ws.audioscrobbler.com/2.0/?api_key=YOUR_API_KEY&method=User.getlovedtracks&user=TyphoonsNotABot&limit=1&format=json
    ```

    ```json
      {
        "lovedtracks": {
          "@attr": {
            "page": "1",
            "total": "7790",
            "user": "TyphoonsNotABot",
            "perPage": "1",
            "totalPages": "7790"
          },
          "track": [
            {
              "artist": {
                "url": "https://www.last.fm/music/The+Backseat+Lovers",
                "name": "The Backseat Lovers",
                "mbid": ""
              },
              "mbid": "59da79dd-aed6-447c-951c-070f6b8446a1",
              "date": {
                "uts": "1603112664",
                "#text": "19 Oct 2020, 13:04"
              },
              "url": "https://www.last.fm/music/The+Backseat+Lovers/_/Davy+Crochet",
              "image": [
                {
                  "size": "small",
                  "#text": "https://lastfm.freetls.fastly.net/i/u/34s/2a96cbd8b46e442fc41c2b86b821562f.png"
                },
                {
                  "size": "medium",
                  "#text": "https://lastfm.freetls.fastly.net/i/u/64s/2a96cbd8b46e442fc41c2b86b821562f.png"
                },
                {
                  "size": "large",
                  "#text": "https://lastfm.freetls.fastly.net/i/u/174s/2a96cbd8b46e442fc41c2b86b821562f.png"
                },
                {
                  "size": "extralarge",
                  "#text": "https://lastfm.freetls.fastly.net/i/u/300x300/2a96cbd8b46e442fc41c2b86b821562f.png"
                }
              ],
              "name": "Davy Crochet",
              "streamable": {
                "fulltrack": "0",
                "#text": "0"
              }
            }
          ]
        }
      }
    ```


??? warning "Example Response of a user that doesn't exist"

    HTTP status: `404 NOT FOUND`

    ```
    https://ws.audioscrobbler.com/2.0/?api_key=YOUR_API_KEY&method=User.getlovedtracks&user=userthatdoesntexist&format=json
    ```

    ```json
    {
        "error": 6,
        "message": "User not found"
    }
    ```

[string]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String
[number]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number
[key]: https://www.last.fm/api/account/create