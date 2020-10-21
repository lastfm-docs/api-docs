Get a list of the user's personal tags.

No authentication required.

## Parameters

| Method        | Type                                                                                              | Default | Optional                      | Description                                         |
| ------------- | ------------------------------------------------------------------------------------------------- | ------- | ----------------------------- | --------------------------------------------------- |
| `user`        | [string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) | `none`  | :negative_squared_cross_mark: | The last.fm username to fetch the personal tags of. |
| `tag`         | [string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) | `none`  | :negative_squared_cross_mark: | The tag that is being fetched.                      |
| `taggingtype` | [string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) | `none`  | :negative_squared_cross_mark: | The type of items that have been tagged. Options are artist / album /track |
| `limit`       | [number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) | 50      | :white_check_mark:            | The page number to fetch. Defaults to first page.   |
| `page`        | [number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) | 1       | :white_check_mark:            | The number of pages to be fetched.                  |
| `api_key`     | [token](https://www.last.fm/api/account/create)                                                   | `none`  | :negative_squared_cross_mark: | A Last.fm API key.                                  |

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

    | Parameter | Value |
    | --------- | ----- |
    | username  | rj |
    | tag     | rock     |
    | taggingtype     | artist     |
    | format    | json  |

    HTTP status: `200 OK`

    ```
    http://ws.audioscrobbler.com/2.0/?method=user.getpersonaltags&user=rj&tag=rock&taggingtype=artist&api_key=YOUR_API_KEY&format=json&limit=1
    ```

    ```json
    {
    "taggings": {
        "artists": {
        "artist": [
            {
            "name": "Jack Bruce",
            "mbid": "94a24504-3548-4bde-a89b-273d277d194e",
            "url": "https://www.last.fm/music/Jack+Bruce",
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
        "user": "RJ",
        "tag": "rock",
        "page": "1",
        "perPage": "1",
        "totalPages": "20",
        "total": "20"
        }
      }
    }
    ```

??? warning "Example response of non existing user"
    HTTP status: `200 OK`

    ```
    http://ws.audioscrobbler.com/2.0/?method=user.getpersonaltags&user=userthatdoesntexist&tag=rock&taggingtype=artist&api_key=YOUR_API_KEY&format=json&limit=1
    ```

    ```json
    {
        "error": 6,
        "message": "User not found"
    }
    ```

??? warning "Example response of a user with no tags as the ones fetched"
    HTTP status: `200 OK`

        ```
        http://ws.audioscrobbler.com/2.0/?method=user.getpersonaltags&user=burdayy&tag=rock&taggingtype=artist&api_key=YOUR_API_KEY&format=json&limit=1
        ```

        ```json
        {
        "taggings": {
            "artists": {
            "artist": [

            ]
            },
            "@attr": {
            "user": "Burdayy",
            "tag": "rock",
            "page": "1",
            "perPage": "1",
            "totalPages": "0",
            "total": "0"
            }
        }
        }
        ```

??? warning "Example response of a tag that does not exist"
    HTTP status: `200 OK`

        ```
        http://ws.audioscrobbler.com/2.0/?method=user.getpersonaltags&user=rj&tag=rock&taggingtype=taggingtypethatdoesntexist&api_key=YOUR_API_KEY&format=json&limit=1
        ```
        ```json

        {
            "error": 6,
            "message": "taggingtype param missing",
            "links": []
        }
        ```
