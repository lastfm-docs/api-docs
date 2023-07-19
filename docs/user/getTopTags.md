Get the top tags used by this user.

No authentication required.

## Parameters
| Method | Type | Default | Required | Description 
| ------ | ---- | ------- | -------- | -----------
| `user` | [string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) | `none` | :white_check_mark: | The Last.fm username to fetch top tags for.
| `limit` | [number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) | 50 | :negative_squared_cross_mark: | The number of results to fetch per page. Defaults to 50.
| `api_key` | [token](https://www.last.fm/api/account/create) | `none` | :white_check_mark: | A Last.fm API key.

## Responses
Errors:

- 6 : Invalid parameters - Your request was either missing a required parameter, the parameter was not found, or had 0 results
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

    | Parameter | Value |
    | --------- | ----- |
    | username  | rj    |
    | limit     | 5     |
    | format    | json  |

    HTTP status: `200 OK`

    ```
    https://ws.audioscrobbler.com/2.0/?method=user.gettoptags&user=rj&api_key=YOUR_API_KEY&format=json&limit=5
    ```

    ```json
    {
        "toptags": {
            "tag": [
                {
                    "name": "rock",
                    "count": "20",
                    "url": "https://www.last.fm/tag/rock"
                },
                {
                    "name": "jazz",
                    "count": "17",
                    "url": "https://www.last.fm/tag/jazz"
                },
                {
                    "name": "metal",
                    "count": "10",
                    "url": "https://www.last.fm/tag/metal"
                },
                {
                    "name": "soul",
                    "count": "8",
                    "url": "https://www.last.fm/tag/soul"
                },
                {
                    "name": "female vocalists",
                    "count": "8",
                    "url": "https://www.last.fm/tag/female+vocalists"
                }
            ],
            "@attr": {
                "user": "RJ"
            }
        }
    }
    
    ```

??? warning "Example response of a user with no tags"
    HTTP status: `200 OK`

    ```
    https://ws.audioscrobbler.com/2.0/?method=user.gettoptags&user=aidan-&api_key=YOUR_API_KEY&format=json
    ```

    ```json
    {
        "toptags": {
            "tag": [],
            "@attr": {
                "user": "aidan-"
            }
        }
    }
    ```

??? warning "Example response of a user that does not exist"
    HTTP status: `200 OK`

    ```
    https://ws.audioscrobbler.com/2.0/?method=user.gettoptags&user=userthatdoesntexist&api_key=YOUR_API_KEY&format=json
    ```

    ```json
    {
        "error": 6,
        "message": "User not found",
        "links": []
    }
    ```