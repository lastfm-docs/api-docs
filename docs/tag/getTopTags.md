Fetches the top global tags on Last.fm. Sorted by popularity. (number of times used)

No authentication required.

## Parameters
| Method | Type | Default | Required | Description 
| ------ | ---- | ------- | -------- | -----------
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
    https://ws.audioscrobbler.com/2.0/?method=tag.getTopTags&tag=metal&api_key=YOUR_API_KEY&format=json
    ```

    ```json
    {
      "toptags": {
        "@attr": {
          "offset": 0,
          "num_res": 50,
          "total": 2804440
        },
        "tag": [
          {
            "name": "rock",
            "count": 4024829,
            "reach": 399440
          },
          {
            "name": "electronic",
            "count": 2441085,
            "reach": 258464
          },
          {
            "name": "seen live",
            "count": 2159269,
            "reach": 82163
          },
          ... and 47 more
        ]
      }
    }
    ```

[key]: https://www.last.fm/api/account/create